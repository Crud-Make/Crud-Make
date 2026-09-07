# 👋 Olá, eu sou Thygo Carvalho

Desenvolvedor fullstack. Construo sistemas de gestão para negócios pequenos que ainda rodam em
planilha — do levantamento da regra com o dono até o app no celular do funcionário.

Meu forte é **TypeScript** — React na web, **React Native** no mobile — e **Node (NestJS), Bun e
Python (FastAPI)** no back, sobre **PostgreSQL**.
Estou me formando em ciência de dados com Python e começando a estudar Go.

## 💻 O que eu faço

- Modelagem do domínio a partir da planilha real do cliente, com a fórmula original reproduzida e
  testada linha a linha contra o dado histórico
- PostgreSQL com RLS em todas as tabelas, migrações versionadas, auditoria por trigger
- APIs e regra de negócio em TypeScript (NestJS, Node/Bun) ou Python (FastAPI), conforme o projeto
- Monorepo com pacote de domínio compartilhado entre painel web e PWAs
- PWA instalável, com notificação push e uso offline; React Native/Expo quando precisa de loja
- Integração de LLM em fluxo de produção quando resolve um problema concreto (OCR de relatório por foto)
- Containerização com Docker e Docker Compose: ambiente de desenvolvimento reproduzível e deploy em
  um comando

## 🤖 Desenvolvimento com IA

Uso Claude Code como parte do processo de engenharia, não como gerador de código solto. No projeto
do posto, o setup versionado no repositório tem:

- **Orquestração de agentes:** seis subagentes especializados por domínio (grafo do código,
  planilha, RLS, conformidade, esquema, histórico do git), cada um com memória própria versionada e
  roteados automaticamente pelo tipo de pergunta
- **Travas automáticas (hooks):** escrita em dado real negada, `push --force` negado, commit com
  fórmula sem golden master pergunta antes — 131 casos de teste cobrindo os próprios hooks
- **Grafo de conhecimento do código:** o repositório inteiro (TypeScript, SQL, políticas de RLS)
  indexado como grafo por AST, reconstruído a cada commit por hook; o agente localiza no grafo e
  confirma no arquivo antes de responder — grafo é hipótese, nunca resposta
- **Loop engineering:** o ciclo propõe → trava verifica → teste decide, fechado por automação —
  hook `PreToolUse` que bloqueia antes do erro, hook `PostToolUse` que cobra o golden master na
  hora da edição, roteamento de pergunta para o agente certo sem intervenção manual
- **Engenharia de contexto:** o que cada agente vê é decidido no repositório — `CLAUDE.md` como
  fonte de verdade do processo, skill de domínio injetada no subagente pelo frontmatter, memória
  por agente versionada e datada, e um hook que força delegação quando a thread principal começa a
  ler demais. Contexto pequeno e certo, não grande e genérico
- **MCP (Model Context Protocol):** servidores do Supabase e do GitHub ligados ao agente; o do banco
  roda em `--read-only` com as ferramentas de mutação (`apply_migration`, deploy, branches) em lista
  de negação — DDL contra produção só por script versionado, nunca pelo chat
- **Skills de domínio versionadas:** regra de negócio, ETL da planilha, critério de "pronto" — o
  agente lê a regra do repositório, não da memória
- Resultado: um monorepo com três apps e 3.296 asserções contra dado real, entregue e em produção
  por uma pessoa

## 📌 Projetos

### ⛽ Posto Providência — caixa e gestão de posto de combustível

Em uso diário desde agosto/2026. Os frentistas fecham o caixa pelo celular; o painel concilia contra
o encerrante das bombas; o dono acompanha o mês.

- Monorepo Bun: painel do gerente (React 19 + Vite), PWA do frentista, PWA do dono
- PostgreSQL com RLS em 100% das tabelas, migrações versionadas, funções serverless (OCR com Gemini
  Vision, push)
- 3.296 asserções de golden master contra a planilha que o posto usava antes
- Fechamento por turno e frentista, custo médio do mês, rateio de despesa por litro, lucro por
  produto, estoque teórico × régua

🌐 Sistema em produção: https://posto-providencia.vercel.app (acesso por login — o dono e os frentistas)

Repositório privado — contém o financeiro real do cliente. Demonstração sob pedido.

### 🧾 [ProvControl](https://github.com/Crud-Make/Provcontrol) — controle de caixa multi-posto

PHP 8.5 / Laravel 13. Leituras e vendas do concentrador, valores conferidos por frentista,
pagamentos eletrônicos e taxas, fechamento diário, isolamento por posto.

### 📱 [posto-mobile](https://github.com/Crud-Make/posto-mobile) — app do frentista

React Native / Expo. Abertura e fechamento de turno, venda por bico, fiado, validação de voucher,
push, atualização por EAS Update.

### 💰 [axxy-finance](https://github.com/Crud-Make/axxy-finance) — finanças pessoais

Python (FastAPI) + React, Docker. Categorização de lançamentos com IA.

### 📊 Ciência de dados

Em andamento. O repositório com os estudos e as análises entra aqui em breve.

## 🚀 Tecnologias & Ferramentas

**⚙️ Backend**
- Node.js / Bun
- TypeScript
- NestJS
- Python / FastAPI
- PHP / Laravel
- REST API
- Autenticação JWT e PKCE
- Funções serverless (Edge Functions)
- Notificações push (Web Push)
- Integrações com APIs externas (Gemini Vision, Google APIs)

**🎨 Frontend**
- TypeScript / JavaScript
- React 19
- Next.js
- Vite
- Tailwind CSS
- PWA (Workbox, offline, instalável)
- HTML5 / CSS3

**📱 Mobile**
- React Native
- Expo (EAS Build / EAS Update)
- Push notifications

**🗄️ Banco de Dados**
- PostgreSQL
- MySQL
- SQLite
- Row-Level Security (RLS)
- Triggers e auditoria
- Migrações versionadas
- Modelagem relacional

**🐳 DevOps & Ferramentas**
- Docker / Docker Compose
- Git / GitHub
- CI/CD (GitHub Actions)
- Vercel
- Linux (Arch)
- Shell script

**✅ Testes & Qualidade**
- Vitest
- PHPUnit
- Golden master contra dado real
- ESLint / TypeScript strict

**🤖 Desenvolvimento com IA**
- Claude Code (subagentes, hooks, skills versionadas)
- Orquestração de agentes
- Grafo de conhecimento do código (AST, graphify)
- Loop engineering (hooks de verificação, gates automáticos)
- Engenharia de contexto (CLAUDE.md, skills, memória versionada por agente)
- MCP — Model Context Protocol (Supabase, GitHub; servidores em modo somente leitura)
- LLM em produção (OCR com Gemini Vision)

**🏗️ Arquitetura & Boas Práticas**
- Monorepo com pacote de domínio compartilhado
- Feature-Sliced Design
- MVC
- Clean Code / SOLID
- Data Mapper na fronteira banco ↔ UI
- Modelagem de dados a partir da regra real do negócio
- ETL auditável

**📚 Estudando**
- Ciência de dados (Python, pandas, estatística)
- Go

## 📫 Contato

🐙 GitHub: [Crud-Make](https://github.com/Crud-Make) · 💼 LinkedIn: em breve
