## Passo a Passo: Plataforma Omnichannel de Freelancers

### Fase 1: Infraestrutura e Containers (O Alicerce)

Antes de escrever qualquer código, você precisa do ambiente rodando. Como a orquestração será fundamental, tudo deve nascer conteinerizado.

1. **Subir o Banco de Dados:** Configure um container com o PostgreSQL para ser a fonte da verdade do seu sistema. Crie as tabelas principais: `Usuarios` (clientes e freelas), `Projetos` (com colunas de status como `RASCUNHO`, `PENDENTE`, `PUBLICADO`) e `Propostas`.
2. **Subir a Mensageria:** Adicione a **Evolution API** no seu `docker-compose.yml`. Ela será a ponte não-oficial e gratuita para o WhatsApp.
3. **Subir o Maestro:** Adicione o **n8n** no mesmo compose. Ele precisa estar na mesma rede Docker para conversar facilmente com a Evolution API e o seu banco/backend.

### Fase 2: O Backend Core (Node.js)

Seu backend Node.js não vai lidar com a IA diretamente; ele será a "API de Negócios" e o guardião do banco de dados.

1. **Criar os Endpoints de Recepção:** Crie uma rota (ex: `POST /api/projetos/webhook-n8n`) exclusiva para receber os dados limpos que o n8n vai enviar.
2. **Gerenciamento de Estado:** Crie a lógica de atualização de status. Quando o Node.js recebe um projeto novo via webhook, ele salva no Postgres com o status `RASCUNHO`.
3. **Endpoints do Frontend:** Desenvolva as rotas tradicionais (`GET /api/projetos`, `PUT /api/projetos/:id`) para que a plataforma web (o painel do cliente) possa consumir, editar e aprovar os projetos.

### Fase 3: O Fluxo de Inteligência no n8n (A Mágica)

Aqui é onde a experiência do usuário se transforma. O n8n fará o meio de campo entre o WhatsApp e os LLMs.

1. **Gatilho de Entrada:** Configure um nó de *Webhook* no n8n para receber todas as mensagens da Evolution API.
2. **Roteamento por Tipo de Mídia (Switch Node):**
* **Se for Áudio:** Envie o arquivo para a API da **Groq** (usando o modelo Whisper). A Groq (LPU) é brutalmente rápida, o que garante que o cliente não fique esperando a transcrição.
* **Se for Imagem/Texto:** Passe direto para o próximo passo.


3. **Extração Estruturada (Gemini):** Junte a transcrição do áudio (ou o texto/imagem original) e envie para o **Gemini** via chamada de API.
* *Prompt Sistêmico:* "Você é um analista de requisitos. Extraia da mensagem do usuário os seguintes campos e retorne ESTRITAMENTE em formato JSON: `titulo`, `descricao_tecnica`, `orcamento_estimado`, `tecnologias_sugeridas`, `prazo`. Se faltar algo crítico, preencha com 'N/A'."


4. **Validação Lógica:** O n8n verifica o JSON retornado pelo Gemini. Se houver muitos "N/A", o n8n devolve uma pergunta para o WhatsApp do cliente pedindo mais detalhes. Se estiver completo, ele dispara o JSON para o endpoint do seu backend Node.js.

### Fase 4: O Loop Omnichannel (Aprovação)

O cliente precisa ter o poder de escolha de onde aprovar a demanda.

1. **Notificação com Botões:** Após o backend confirmar que salvou o projeto, o n8n dispara uma mensagem interativa de volta para o WhatsApp do cliente.
* *Mensagem:* "Rascunho criado! Título: [X], Orçamento: [Y]. O que deseja fazer?"
* *Botões:* `[Aprovar e Publicar]` | `[Editar no Site]` | `[Cancelar]`


2. **Ação via WhatsApp:** Se ele clica em "Aprovar", a Evolution API manda outro webhook pro n8n, que avisa o Node.js: "Altere o status do projeto ID X para PUBLICADO".
3. **Ação via Web:** Se ele clica em "Editar no Site", o botão envia um link parametrizado (ex: `ggfreela.dev/painel/projeto/123`). Ao abrir, ele consome a API Node.js, edita o texto e aprova direto pelo navegador.

### Fase 5: Curadoria e Distribuição (O Pós-Publicação)

Com o projeto público, os freelancers entram em cena.

1. **Recepção de Propostas:** Freelancers enviam propostas pelo site (salvas no Postgres via Node.js).
2. **Motor de Curadoria:** Você pode usar o próprio backend Node.js (ou um script secundário em Python rodando via *cronjob*) para avaliar as propostas em background. Ele pode bater na API do Gemini passando a descrição do projeto e a proposta do freela para gerar um *Score de Match* (0 a 100).
3. **Alerta de Valor:** Quando o Node.js identifica que o projeto atingiu 3 propostas com *Score > 80*, ele aciona o n8n novamente para mandar uma notificação no WhatsApp do cliente: "Você tem 3 propostas excelentes esperando sua avaliação no painel!".

---

Essa estrutura separa responsabilidades: o banco de dados e as regras de negócio ficam protegidos no Node.js, as integrações pesadas e condicionais ficam visuais no n8n, e a inteligência é delegada para as APIs específicas.

Gostaria de começar pela infraestrutura? Posso montar o `docker-compose.yml` base contendo o PostgreSQL, n8n e Evolution API para você dar o pontapé inicial.