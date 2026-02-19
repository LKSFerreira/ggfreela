# 🎮 GGFreela.dev

> **O fim do *pay-to-win* no mercado de freelancers.**
> Plataforma open-source focada em conectar clientes e desenvolvedores através de um modelo justo, sem taxas abusivas, sem pedágios de aprovação e com moderação inteligente via IA.

[![Status](https://img.shields.io/badge/status-em_desenvolvimento-orange)]()
[![Stack](https://img.shields.io/badge/stack-Spring_Boot_%7C_PostgreSQL-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

## 🛑 O Problema (Por que o GGFreela existe?)
O mercado tradicional de freelancers quebrou. Plataformas gigantes cobram taxas de até 20% sobre o trabalho suado do desenvolvedor, além de exigirem assinaturas mensais ou "pedágios" (R$ 50+) apenas para aprovar um perfil e permitir a entrada em um leilão de preços degradante. 

O GGFreela nasceu do "Rage Quit" contra esse sistema. Desenvolvedores não deveriam pagar para ter o privilégio de trabalhar.

## 💡 A Solução (Fair Play)
Um ecossistema transparente onde a tecnologia trabalha a favor da comunidade:
* **Zero Pedágios:** Seu portfólio e suas habilidades ditam seu espaço, não o seu cartão de crédito.
* **Moderação Implacável com IA:** Chega de competir com agências usando bots de spam. Nossa IA analisa e barra propostas genéricas ou orçamentos predatórios em milissegundos.
* **Foco no Código:** Comunicação centralizada, sistema de Escrow (garantia) seguro e histórico imutável de ações.

## 🛠️ Stack Tecnológica
Este projeto foi construído pensando em escalabilidade, segurança e integração com IA de ponta:

* **Backend Orquestrador:** Java 21 + Spring Boot 3
* **Banco de Dados:** PostgreSQL (com Triggers nativos para logs de auditoria)
* **Inteligência Artificial:** Integração via API (Google Gemini / Vertex AI / Groq) para análise de sentimento e anti-spam.
* **Infraestrutura:** Docker & DevContainers para um ambiente de desenvolvimento isolado e padronizado.
* **Deploy/Cloud:** Arquitetado para rodar em *Free Tiers* (Oracle Cloud ARM) ou soluções *Serverless*.

## 🚀 Como rodar o projeto localmente

1. Clone o repositório:
```bash
   git clone [https://github.com/SEU_USUARIO/ggfreela.git](https://github.com/SEU_USUARIO/ggfreela.git)
```

2. Suba a infraestrutura de banco de dados via Docker:
```bash
docker-compose -f .devcontainer/compose.yaml up -d
```

3. Execute a aplicação Spring Boot:
```bash
./mvnw spring-boot:run
```

## 🤝 Contribuindo

Este projeto é de desenvolvedores para desenvolvedores. Se você também está cansado das taxas abusivas, sinta-se à vontade para abrir uma *Issue* ou enviar um *Pull Request*. Toda ajuda na construção do frontend, refinamento da IA ou regras de negócio do backend é bem-vinda.

---

*Built with 😈💻 and lots of coffee.*