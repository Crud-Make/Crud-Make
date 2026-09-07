# Thygo Carvalho

**Desenvolvedor fullstack especializado em ecossistemas integrados** — web, mobile e painel
administrativo operando sobre um único domínio de dados, em vez de apps isolados que precisam ser conciliados
depois.

O que eu entrego:

- **Integração mobile ↔ painel:** o que entra pelo celular já está no painel, sem sincronização
  manual, sem planilha intermediária
- **Cruzamento de dados:** fontes diferentes (operação, financeiro, estoque, leitura de
  equipamento) convergindo num modelo só, com regra de negócio testada contra o histórico real
- **Um domínio, vários apps:** pacote compartilhado entre painel administrativo, PWA e React
  Native — a fórmula existe uma vez e roda igual em todos

TypeScript de ponta a ponta (React, React Native, NestJS/Bun) sobre PostgreSQL. Python (FastAPI)
quando o projeto pede. Claude Code como parte do processo de engenharia, com travas automáticas
que impedem o agente de errar em produção.

---

## ⛽ Posto Providência — gestão de posto de combustível

**Em produção desde agosto/2026.** Os frentistas fecham o caixa pelo celular, o painel concilia
contra o encerrante das bombas, o dono acompanha o mês. Entregue por uma pessoa.

- **3.296 asserções de golden master** contra a planilha que o posto usava antes — cada fórmula
  reproduzida e validada contra o histórico real
- Monorepo Bun com três apps: painel do gerente (React 19 + Vite), PWA do frentista, PWA do dono,
  compartilhando um pacote de domínio único
- PostgreSQL com RLS em 100% das tabelas, migrações versionadas, auditoria por trigger
- Funções serverless: OCR de relatório por foto (Gemini Vision) e Web Push
- Fechamento por turno e frentista, custo médio do mês, rateio de despesa por litro, lucro por
  produto, estoque teórico × régua

🌐 https://posto-providencia.vercel.app (acesso por login) · Repositório privado — contém o
financeiro real do cliente. Demonstração sob pedido.

### Como a IA entra no processo

O setup do Claude Code está versionado no repositório e funciona como parte do time, não como
gerador de código solto:

- **Travas (hooks):** escrita em dado real negada, `push --force` negado, commit de fórmula sem
  golden master exige confirmação. Os próprios hooks têm 131 casos de teste.
- **Seis subagentes por domínio** (grafo do código, planilha, RLS, conformidade, esquema,
  histórico do git), cada um com memória própria versionada, roteados pelo tipo de pergunta.
- **Grafo do código por AST** (TypeScript, SQL, políticas RLS), reconstruído a cada commit. O
  agente localiza no grafo e confirma no arquivo — grafo é hipótese, nunca resposta.
- **MCP em modo seguro:** Supabase em `--read-only`, ferramentas de mutação em lista de negação.
  DDL contra produção só por script versionado.
- **Contexto pequeno e certo:** `CLAUDE.md` como fonte de verdade do processo, skills de domínio
  injetadas por frontmatter, hook que força delegação quando a thread principal lê demais.

O ciclo é: agente propõe → trava verifica → teste decide.

---

## 📌 Outros projetos

**[ProvControl](https://github.com/Crud-Make/Provcontrol)** — controle de caixa multi-posto.
PHP 8.5 / Laravel 13. Leituras do concentrador, conferência por frentista, pagamentos eletrônicos
e taxas, isolamento por posto.

**[posto-mobile](https://github.com/Crud-Make/posto-mobile)** — app do frentista.
React Native / Expo. Turno, venda por bico, fiado, voucher, push, EAS Update.

**[axxy-finance](https://github.com/Crud-Make/axxy-finance)** — finanças pessoais.
FastAPI + React, Docker. Categorização de lançamentos com IA.

---

## 🛠️ Stack

| | |
|---|---|
| **Backend** | TypeScript (NestJS, Bun), Python (FastAPI), PHP (Laravel), PostgreSQL com RLS, Edge Functions, Web Push |
| **Frontend** | React 19, Next.js, Vite, Tailwind, PWA (Workbox, offline) |
| **Mobile** | React Native, Expo (EAS Build/Update) |
| **Testes** | Vitest, PHPUnit, golden master contra dado real |
| **DevOps** | Docker Compose, GitHub Actions, Vercel, Linux (Arch) |
| **IA** | Claude Code (subagentes, hooks, skills), MCP, grafo de código por AST, LLM em produção |

**Estudando:** ciência de dados (Python, pandas, estatística) e Go.

---

🐙 [github.com/Crud-Make](https://github.com/Crud-Make)
