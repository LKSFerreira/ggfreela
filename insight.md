# 📜 insight.md: GGFreela.dev

*Versão: 0.3 | Status: Definição de Arquitetura, Dores e Moderação via IA*

### 1. A Origem (O Estopim)

O projeto nasceu da frustração com o modelo "pay-to-win" das plataformas de freelancer. A gota d'água foi a cobrança de um "pedágio" (R$ 52,90) apenas para acelerar a aprovação de perfis. O desenvolvedor não deve pagar para ter o privilégio de procurar trabalho e entrar em leilões de preços.

### 2. O Nome e a Filosofia

* **Nome:** GGFreela.dev
* **Objetivo:** Criar um ecossistema justo (Fair Play). A plataforma não visa o enriquecimento dos criadores, mas **deve** ser autossustentável: se escalar, as receitas geradas devem cobrir os custos de infraestrutura sem explorar os usuários.

### 3. Stack Tecnológico e Infraestrutura

* **Backend Orquestrador:** Java com Spring Boot.
* **Inteligência Artificial (Moderação):** Integração via API (Gemini, GroqCloud ou Vertex AI) gerenciada pelo Spring Boot. A IA atuará como "juíza" automatizada para analisar perfis e propostas, barrando spam e orçamentos predatórios em milissegundos.
* **Hospedagem (Plano A):** Oracle Cloud (Free Tier) com máquina ARM de 24GB para suportar a JVM.
* **Hospedagem (Plano B - Fallback):** Render / Koyeb via Docker.
* *Estratégia Anti-Cold Start:* A Landing Page fará requisições assíncronas (pings invisíveis) para acordar o servidor enquanto o usuário navega.


* **Banco de Dados:** PostgreSQL (via Supabase ou auto-hospedado), utilizando Triggers nativos para logs de auditoria imutáveis.

### 4. Análise de Dores e Oportunidades (O que vamos resolver)

#### 🔴 As Dores dos Freelancers

1. **Cobrança para existir:** Fim das assinaturas mensais ou "pedágios" de aprovação.
2. **Leilão Reverso (Prostituição):** Bloqueio ativo de clientes que aceitam propostas com valores degradantes.
3. **A Taxa Abusiva no Fim:** Fim das plataformas que mordem 20% do valor final do projeto.
4. **Concorrência com Bots/Spam:** Disputar vagas com agências que usam robôs. (Resolvido pela nossa moderação com IA).

#### 🔴 As Dores dos Clientes

1. **Enxurrada de Spam:** Receber 50 propostas copiadas e coladas que não leem a descrição. (Resolvido pela IA).
2. **Falta de Filtro de Qualidade:** Dificuldade em atestar a capacidade técnica do freelancer.
3. **Abandono de Projeto:** O freelancer pega o projeto e some.

#### 🟢 O Que Funciona Hoje (O que vamos manter)

1. **Escrow (Garantia de Pagamento):** O cliente deposita antes. O dev trabalha com segurança, o cliente só libera ao receber.
2. **Comunicação Centralizada:** Histórico de conversas gravado no banco para evitar problemas de escopo.

### 5. O Modelo de Negócios

* Para detalhes sobre como a plataforma será sustentável (como vamos pagar os custos de servidor sem cobrar mensalidades ou taxas abusivas), consulte o documento dedicado: [monetizacao.md](./monetizacao.md)