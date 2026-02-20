# 🛡️ Política Anti-Fraude e Tolerância Zero (Multi-Contas)

*Status: Diretrizes de Segurança | Princípio: Esmagando o Sistema de "Farm Fake"*

O ecossistema justo do **GGFreela** só sobrevive se os dados forem reais. Plataformas tradicionais estão infestadas de desenvolvedores que criam contas "Clientes Fakes" para contratar a si mesmos, forjar projetos concluídos perfeitos e inflar artificialmente as próprias avaliações (5 estrelas). No GGFreela, as consequências e a detecção são impiedosas.

## 1. A Regra de Ouro: Uma Conta, Uma Pessoa/CNPJ
É **estritamente proibido** que a mesma entidade jurídica ou física posssua múltiplas contas na plataforma com o intúito de burlar o sistema de matching, o farm de GGCoin ou a nota de avaliação.
*   **A Punição:** O termo é **Tolerância Zero**. Se o sistema confirmar (sem falsos positivos) a existência de uma *farm/ring* de contas falsas, **todas as contas atreladas** (tanto a do "Cliente" quanto a do "Dev" beneficiado) sofrerão **Banimento Permanente Imediato**, com confisco total do saldo de GGCoin de ambas as partes.

## 2. Como o Sistema Pega os Fraudadores (A "Malha Fina" Tech)
Para garantir que o banimento só aconteça quando há certeza absoluta (evitando punir injustamente IPs públicos ou de coworking), a plataforma usa uma malha fina de 3 camadas (*Triangulação Heurística*).

### Camada 1: Assinatura de Rede e Aparelho (Fingerprinting Base)
Não avaliamos apenas se o "IP é o mesmo", mas uma composição cruzada:
*   **IP e Sub-Redes recorrentes.**
*   **Browser Fingerprinting:** Fontes instaladas, resolução, Canvas/Webgl fingerprint, fuso horário, etc.
*   **Sessão Concorrente:** O Dev A e o Cliente B costumam fazer *login* no exato mesmo segundo usando a mesma máquina? (Essa é a falha clássica de fraude de abas anônimas).

### Camada 2: Análise Comportamental por IA (O Padrão GGFreela)
Aqui é onde pegamos ferramentas complexas como VPNs ou VMs. A nossa IA (Gemini/Vertex) avalia o metadado relacional entre as duas contas suspeitas.
*   **O "Tempo de Digitação":** Um escopo de projeto gigantesco foi postado pelo "Cliente" e exatos 3 segundos depois o "Dev Bot" enviou uma proposta de 4 páginas de volta. É inumano ler e orçar tão rápido. Flag levantada.
*   **Histórico Fechado (Silo):** O Cliente "X" está há 8 meses na plataforma, publicou 10 projetos, e **misteriosamente**, o Dev "Y" ganhou todos os 10 projetos, mesmo quando Devs com nota superior enviaram propostas mais baratas.
*   **Conversação Nula:** Um projeto de R$ 5.000,00 foi fechado no sistema Escrow. A plataforma verifica os logs de chat e vê que o cliente mandou um *"Oi"* e o dev um *"Pronto"*, e enviaram o projeto. Zero discussão técnica, zero iterações. Flag gigante.

### Camada 3: Validação de Pagamento Escrow (A Prova de Fogo)
Antes de banir, olhamos para onde o dinheiro está indo.
*   O Cliente pagou a garantia usando um cartão de crédito no nome do próprio Freelancer contratado? (Golpe clássico mapeado e bloqueado no gateway).
*   Se o CPF/CNPJ de saque da conta do "Cliente X" que desistiu de projetos na plataforma cruza com o CPF de depósito do "Dev Y".

---

## 3. Punição Limpa e Transparente
A plataforma GGFreela não bane "na surdina" (Shadowban) de forma covarde e incompreensível. 
Uma vez que a Triangulação atesta a fraude das contas A e B com 99% de precisão (IP correspondente + Silo de Contratações Isoladas + Pagamento cruzado), o acesso é bloqueado na tela de login com uma mensagem crua e honesta:
> *"Sua conta e a conta associada '[Nome do Fake]' foram permanentemente banidas sob o artigo X - Criação de Farm de Avaliação"* (Podemos polir o texto final). 

Não há segunda chance para manipular a confiança dos usuários honestos do ecossistema.
