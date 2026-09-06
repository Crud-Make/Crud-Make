# Thygo Carvalho

Desenvolvedor fullstack. Construo sistemas de gestão para negócios pequenos que ainda rodam em
planilha — do levantamento da regra com o dono até o app no celular do funcionário.

Trabalho principalmente com **TypeScript, React e Supabase (Postgres)**. Também escrevo Python e PHP
quando o projeto pede.

## O que eu faço

- Modelagem do domínio a partir da planilha real do cliente, com a fórmula original reproduzida e
  testada linha a linha contra o dado histórico
- Postgres com RLS em todas as tabelas, migrações versionadas, auditoria por trigger
- Monorepo com pacote de domínio compartilhado entre painel web e PWAs
- PWA instalável, com notificação push e uso offline; React Native/Expo quando precisa de loja
- Integração de LLM em fluxo de produção quando resolve um problema concreto (OCR de relatório por foto)

## Projetos

### Posto Providência — caixa e gestão de posto de combustível

Em uso diário desde agosto/2026. Os frentistas fecham o caixa pelo celular; o painel concilia contra
o encerrante das bombas; o dono acompanha o mês.

- Monorepo Bun: painel do gerente (React 19 + Vite), PWA do frentista, PWA do dono
- Supabase: Postgres, RLS em 100% das tabelas, Edge Functions (OCR com Gemini Vision, push)
- 3.296 asserções de golden master contra a planilha que o posto usava antes
- Fechamento por turno e frentista, custo médio do mês, rateio de despesa por litro, lucro por
  produto, estoque teórico × régua

Repositório privado — contém o financeiro real do cliente.

### [posto-mobile](https://github.com/Crud-Make/posto-mobile) — app do frentista

React Native / Expo. Abertura e fechamento de turno, venda por bico, fiado, validação de voucher,
push, atualização por EAS Update.

### [ProvControl](https://github.com/Crud-Make/Provcontrol) — controle de caixa multi-posto

PHP 8.5 / Laravel 13. Leituras e vendas do concentrador, valores conferidos por frentista,
pagamentos eletrônicos e taxas, fechamento diário, isolamento por posto.

### [axxy-finance](https://github.com/Crud-Make/axxy-finance) — finanças pessoais

FastAPI + React, Docker. Categorização de lançamentos com IA.

## Stack

| | |
|---|---|
| Linguagens | TypeScript, Python, PHP, SQL |
| Frontend | React 19, Vite, Tailwind, PWA (Workbox), React Native/Expo |
| Backend | Supabase (Postgres, RLS, Edge Functions), Bun, Node.js, FastAPI, Laravel |
| Testes | Vitest, golden master contra dado real, GitHub Actions |
| Infra | Docker, Vercel, Linux |

## Contato

GitHub: [Crud-Make](https://github.com/Crud-Make) · LinkedIn: em breve
