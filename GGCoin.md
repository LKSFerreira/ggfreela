# 🪙 GGCoin (Economia Interna e Gamificação)

*Status: Definição de Regras | Princípio: Engajamento sem inflação*

A **GGCoin (GGC)** é a moeda virtual do ecossistema GGFreela. Semelhante a moedas de jogos, ela é "farmada" gratuitamente pelo usuário através de missões comportamentais, engajamento e conclusão de projetos reais na plataforma.

**Regra de Ouro (Proteção Jurídica e Econômica):** GGCoin **NÃO PODE** ser comprada diretamente com dinheiro real (fiat). Assinaturas Premium podem ser compradas com dinheiro real, ou serem trocadas pelos GGCs farmados. Por ser um *Utility Token* puramente comportamental e interno, a plataforma detém segurança jurídica para aplicar mecânicas de expiração (decay) sem configurar retenção indevida ou problemas legais.

O objetivo da moeda **não é** permitir que o desenvolvedor compre vantagens algorítmicas (Pay-to-Win), mas sim permitir que ele compre "Recursos de Qualidade de Vida" (QoL) dentro da plataforma, incluindo o pagamento da própria Assinatura Premium.

## 1. Como Farmar GGCoin (Missões e Engajamento)
Para evitar que a economia do GGFreela quebre, as formas de ganho são divididas entre **Missões Recorrentes** (marketing orgânico e retenção) e **Conquistas/Badges** (marcos históricos no perfil).

### A) Missões Recorrentes (Farm Semanal Limitado - Hard Cap)
Ações focadas no crescimento da plataforma e retenção orgânica do Dev. Para evitar bots rodando o tempo inteiro, existe um **Teto Máximo (Cap)** de quantas moedas o usuário pode extrair semanalmente neste nível:
*   **Embaixador Social (Semanal):** Compartilhar um link de um projeto aberto na vitrine ou o próprio perfil do GGFreela no X/Twitter ou Instagram com a hashtag oficial. (Ex: +10 GGC por rede).
*   **Daily Login (Streak Semanal):** Fazer login por 7 dias seguidos e visualizar perfis/projetos ou deixar comentários estruturados. (Ex: +5 GGC ou ticket de sorteio).

### B) Recompensas de Trabalho (Core do Negócio)
A injeção mais pesada de moedas acontece quando o objetivo principal da plataforma é cumprido:
*   **Projeto Concluído com Sucesso:** Toda vez que um projeto for entregue através do Escrow, sem disputas, e com nota total de avaliação:
    *   O Desenvolvedor recebe uma recompensa fixa de **+X GGC**.
    *   O Cliente recebe **+Y GGC** (Incentivando o cliente a continuar na plataforma e a usar suas moedas para destacar seus futuros anúncios de projetos de forma gratuita).
    *   Ganho de **+Z GGC** por realizar avaliações, tanto o cliente quanto o Dev.

### B) Conquistas & Badges (One-Shot com Recompensa Alta)
As conquistas dão o Badge visual definitivo para o perfil + uma injeção única de GGCoin. Algumas delas possuem níveis crescentes (Tiers):
*   **Caçador de Recompensas:** Trazer um Cliente novo pelo seu link de indicação, e esse cliente publicar o primeiro escopo. (Ex: +50 GGC e Badge "Scout").
*   **Embaixador Dev:** Trazer um novo Dev que faça a primeira proposta válida. (Ex: +25 GGC e Badge "Recrutador").
*   **Caçador de Bugs (Tiered):**
    * Nível 1: Reportar 1 bug real confirmado. (Ex: +25 GGC e Badge "Caçador de Mariposas").
    * Nível 2: Reportar 5 bugs. (Ex: +50 GGC e Badge "Entomologista").
    * Nível 3: Sugerir Feature Crítica Implementada. (Ex: +150 GGC e Badge "Arquiteto").
*   **Open Source Contributor (A Vitrine Aberta):** O Dev adicionou/doou um projeto próprio (um boilerplate ou script solto) preenchendo o link do seu repositório. A plataforma usará a **API do GitHub** para integrar, ler o README e criar um card dinâmico super bonito na nossa "Vitrine Pública", para quem quiser clonar e dar estrela invés de contratar. (Ex: +350 GGC e Badge "Sócio de Coração").

---

## 2. Onde Gastar GGCoin (A Lojinha)
A economia só funciona se houver queima de moeda (Sink). O que o Dev pode comprar com GGC?

*   **Pagar a Assinatura Nexus (Mensalidade):** Em vez de pagar no cartão de crédito o valor detalhado no plano, o Dev ativo no farm pode trocar X GGC pelo mês de Assinatura. (Consulte os valores atuais no documento principal: [monetizacao.md](./monetizacao.md)).
*   **Taxa de Conveniência (Saque Pix):** Isentar a taxa do saque imediato (caso ele já tenha gasto o benefício grátis mensal).
*   **Análise de Perfil por IA (One-shot):** Gastar moedas para a IA da plataforma rodar um *scan* no seu portfólio e currículo e apontar: *"Sua taxa de conversão em clientes corporativos está baixa porque falta a palavra-chave Cloud no seu resumo"*.
*   **Destacar Proposta (Sinalizador Visual):** Gastar moedas para colocar um "Sinalizador Visual" (ex: uma borda colorida da plataforma ou ícone brilhante) na sua proposta. **Atenção:** Isso é estritamente cosmético para chamar a atenção visual do cliente. A ordem (o ranking técnico de qual proposta aparece primeiro) continuará sendo ditada **exclusivamente** pela IA de match. Ninguém "compra" o topo.
*   **Cosméticos de Perfil:** Banners para o perfil, cores diferenciadas no *handle* do usuário (Discord style).

---

## 3. Travas de Segurança (Anti-Inflação e Concorrência Desleal)
Para manter o ecossistema GGCoin saudável a longo prazo, teremos regras sistêmicas inquebráveis:
*   **Tolerância Zero para Multi-Contas:** É rigorosamente proibido um Dev ou Cliente criar múltiplas contas para abusar do sistema de indicações, farmar likes/projetos falsos para si mesmo ou manipular taxas. O sistema usará cruzamento de IP, Hardware ID e heurística de IA. Se pego na auditoria: **Banimento Permanente imediato das contas envolvidas**. Para o nível detalhado de regras anti-bots e como a plataforma vasculha isso, leia a política dedicada: [anti_fraude.md](./anti_fraude.md).
*   **Validade da Moeda (Decay System):** Moedas paradas estrangulam qualquer economia virtual. Como GGC não é atrelada a compra em Reais (Fiat), as moedas *farmadas* têm um prazo de validade (Ex: 90 dias após ganhas) ou sofrem uma taxa percentual de expiração se a conta ficar inativa por muito tempo. Isso obriga o usuário a queimar a moeda na Lojinha.
*   **Nunca Vender Vantagem Algorítmica (Vitrine Justa):** 100.000 GGCs não podem comprar a "vaga no topo da lista" de uma proposta de cliente. A classificação original das propostas permanece estritamente baseada em *Match Técnico* de IA e Reputação de Projetos do Dev.
*   **Elasticidade de Preços:** A "inflação" controlada existirá ajustando-se silenciosamente os valores de *Reward* (ganho nas missões) e *Cost* (custo na Lojinha), controlando a oferta circulante da GGCoin.
