# Thygo Carvalho

Desenvolvedor fullstack. Construo sistemas de gestão para negócios pequenos que ainda rodam em
planilha — do levantamento da regra com o dono até o app no celular do funcionário.

Meu forte é **TypeScript** — React na web, **React Native** no mobile — e **Laravel, Node e Bun** no
back, sobre **PostgreSQL**.
Estou me formando em ciência de dados com Python e começando a estudar Go.

## O que eu faço

- Modelagem do domínio a partir da planilha real do cliente, com a fórmula original reproduzida e
  testada linha a linha contra o dado histórico
- PostgreSQL com RLS em todas as tabelas, migrações versionadas, auditoria por trigger
- APIs e regra de negócio em Laravel ou em TypeScript (Node/Bun), conforme o projeto
- Monorepo com pacote de domínio compartilhado entre painel web e PWAs
- PWA instalável, com notificação push e uso offline; React Native/Expo quando precisa de loja
- Integração de LLM em fluxo de produção quando resolve um problema concreto (OCR de relatório por foto)
- Containerização com Docker e Docker Compose: ambiente de desenvolvimento reproduzível e deploy em
  um comando

## Desenvolvimento com IA

Uso Claude Code como parte do processo de engenharia, não como gerador de código solto. No projeto
do posto, o setup versionado no repositório tem:

- **Orquestração de agentes:** seis subagentes especializados por domínio (grafo do código,
  planilha, RLS, conformidade, esquema, histórico do git), cada um com memória própria versionada e
  roteados automaticamente pelo tipo de pergunta
- **Travas automáticas (hooks):** escrita em dado real negada, `push --force` negado, commit com
  fórmula sem golden master pergunta antes — 131 casos de teste cobrindo os próprios hooks
- **Skills de domínio versionadas:** regra de negócio, ETL da planilha, critério de "pronto" — o
  agente lê a regra do repositório, não da memória
- Resultado: um monorepo com três apps e 3.296 asserções contra dado real, entregue e em produção
  por uma pessoa

## Projetos

### Posto Providência — caixa e gestão de posto de combustível

Em uso diário desde agosto/2026. Os frentistas fecham o caixa pelo celular; o painel concilia contra
o encerrante das bombas; o dono acompanha o mês.

- Monorepo Bun: painel do gerente (React 19 + Vite), PWA do frentista, PWA do dono
- PostgreSQL com RLS em 100% das tabelas, migrações versionadas, funções serverless (OCR com Gemini
  Vision, push)
- 3.296 asserções de golden master contra a planilha que o posto usava antes
- Fechamento por turno e frentista, custo médio do mês, rateio de despesa por litro, lucro por
  produto, estoque teórico × régua

Repositório privado — contém o financeiro real do cliente.

### [ProvControl](https://github.com/Crud-Make/Provcontrol) — controle de caixa multi-posto

PHP 8.5 / Laravel 13. Leituras e vendas do concentrador, valores conferidos por frentista,
pagamentos eletrônicos e taxas, fechamento diário, isolamento por posto.

### [posto-mobile](https://github.com/Crud-Make/posto-mobile) — app do frentista

React Native / Expo. Abertura e fechamento de turno, venda por bico, fiado, validação de voucher,
push, atualização por EAS Update.

### [axxy-finance](https://github.com/Crud-Make/axxy-finance) — finanças pessoais

Python (FastAPI) + React, Docker. Categorização de lançamentos com IA.

### Ciência de dados

Em andamento. O repositório com os estudos e as análises entra aqui em breve.

## Stack

| | |
|---|---|
| Linguagens | TypeScript, PHP, Python, SQL |
| Frontend | React 19, Vite, Tailwind, PWA (Workbox) |
| Mobile | React Native, Expo (EAS Build/Update), push notifications |
| Backend | Laravel, Node.js, Bun, FastAPI |
| Banco | PostgreSQL (RLS, triggers, migrações versionadas), MySQL |
| Testes | Vitest, PHPUnit, golden master contra dado real |
| DevOps | Docker, Docker Compose, CI com GitHub Actions, deploy em Vercel, Linux (Arch), shell script |
| IA no processo | Claude Code (subagentes, hooks, skills), orquestração de agentes, Gemini Vision em produção |
| Estudando | Ciência de dados (Python, pandas, estatística), Go |

## Contato

GitHub: [Crud-Make](https://github.com/Crud-Make) · LinkedIn: em breve
