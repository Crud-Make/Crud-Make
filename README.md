# 👋 Olá, eu sou Thygo Carvalho

**Desenvolvedor Fullstack · TypeScript · React · Supabase**
Sistemas de gestão em produção, com IA aplicada onde ela resolve problema de verdade.

Construo sistemas que substituem planilha e papel em negócios reais — do levantamento da regra de
negócio com o dono até o app rodando no celular do funcionário. Gosto de código que dá para auditar:
fórmula com teste contra o dado real, banco com RLS em toda tabela, migração versionada, nada de
número "que parece certo".

---

## 🚀 Tecnologias & Ferramentas

**Linguagens**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

**Frontend**

![React](https://img.shields.io/badge/React_19-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white)
![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)

**Backend & Dados**

![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Bun](https://img.shields.io/badge/Bun-000000?style=for-the-badge&logo=bun&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)

**Qualidade & DevOps**

![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=for-the-badge&logo=vitest&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Linux](https://img.shields.io/badge/Arch_Linux-1793D1?style=for-the-badge&logo=archlinux&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

**IA aplicada**

![Gemini](https://img.shields.io/badge/Gemini_Vision-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white)
![Claude](https://img.shields.io/badge/Claude_Code-D97757?style=for-the-badge&logo=anthropic&logoColor=white)

- Supabase de ponta a ponta: Postgres, **RLS em toda tabela**, políticas testadas, Edge Functions, Realtime, push
- Monorepo com pacote de domínio compartilhado entre apps (web + PWAs), tipos gerados do banco
- **Golden master**: fórmula financeira testada linha a linha contra a planilha real do negócio
- OCR com Gemini Vision (leitura de relatório por foto), com limite de taxa e JWT na função
- Workflows agênticos com Claude Code: hooks que travam erro caro, subagentes por domínio, skills versionadas

---

## 💼 Experiência

**Sistemas de gestão para negócio real**
- Fechamento de caixa por turno e por funcionário, conciliação contra o concentrador de bombas
- Custo médio, rateio de despesa, lucro por produto, estoque teórico × físico
- Cadastro de clientes, fiado, compras por nota, despesas
- Substituição de planilha legada com ETL auditável e reprodução das fórmulas originais

**Mobile e PWA**
- Apps instaláveis no celular do operador, com trabalho offline e notificação push
- React Native / Expo com EAS Update

**Banco de dados e segurança**
- Modelagem relacional, migrações versionadas, RLS e auditoria por trigger
- Auditoria de exposição de banco: o que o papel anônimo alcança, política por política

**Engenharia com IA**
- Integração de LLM em fluxo de produção (visão computacional para leitura de documento)
- Processo de desenvolvimento assistido por agentes, com travas automáticas contra erro de dinheiro

---

## 📌 Projetos em Destaque

### ⛽ Posto Providência — Gestão e caixa de posto de combustível
Sistema em **uso real** desde agosto/2026: os frentistas fecham o caixa pelo celular todo dia e o dono
acompanha o mês pelo painel. Monorepo Bun com três apps sobre o mesmo domínio.

- **Painel do gerente** (React 19 + Vite): relatório diário, planilha do mês, lucro por produto, custos, estoque e tanques
- **PWA do frentista**: fechamento de caixa (dinheiro, PIX, cartão, nota) e régua dos tanques
- **PWA do dono**: encerrante dos bicos **por foto** (OCR com Gemini Vision) e aviso push a cada fechamento
- **Supabase**: Postgres com RLS em todas as tabelas, Edge Functions, migrações versionadas
- **3.296 asserções de golden master** contra a planilha real do posto — a planilha é a fonte de verdade

> Repositório privado (contém o financeiro real do cliente). Prints e demonstração sob pedido.

### 📱 PostoGestão Pro — App mobile do frentista
Interface de pista em **React Native / Expo**: abertura e fechamento de turno, venda por bico,
fiado, validação de voucher, push notifications e atualização sem passar pela loja (EAS Update).

🔗 https://github.com/Crud-Make/posto-mobile

### 🧾 ProvControl — Controle de caixa multi-posto
Versão em **PHP 8.5 / Laravel 13** do controle de caixa: leituras e vendas do concentrador, valores
conferidos por frentista, pagamentos eletrônicos e taxas, fechamento diário e dashboard, com
isolamento explícito por posto.

🔗 https://github.com/Crud-Make/Provcontrol

### 💰 Axxy Finance — Finanças pessoais com IA
Gestão financeira pessoal com **FastAPI + React**, empacotada em Docker com deploy em um comando.

🔗 https://github.com/Crud-Make/axxy-finance

---

## 🎯 Objetivos Profissionais

Busco projetos de **sistemas de gestão, SaaS e integrações** onde a regra de negócio é o difícil —
financeiro, operação, estoque — e onde vale a pena ter teste contra o dado real. Interesse forte em
**Supabase/Postgres, React, arquitetura de monorepo e IA aplicada a processo**.

## 🧠 Diferenciais

✅ Sistema em produção com usuário real, não só projeto de portfólio
✅ Fórmula financeira coberta por golden master contra a fonte original
✅ Segurança de banco como padrão: RLS, políticas testadas, segredo fora do código
✅ Levantamento de requisito direto com o dono do negócio
✅ Desenvolvimento assistido por IA com processo — hooks, revisão, auditoria, não "vibe"
✅ Aprendizado contínuo e documentação do porquê, não só do quê

## 📫 Contato

🐙 GitHub: [github.com/Crud-Make](https://github.com/Crud-Make)
💼 LinkedIn: em breve
📧 Aberto a oportunidades, projetos e parcerias.

---

<div align="center">

![Estatísticas](https://github-readme-stats.vercel.app/api?username=Crud-Make&show_icons=true&theme=tokyonight&locale=pt-br&hide_border=true)
![Linguagens](https://github-readme-stats.vercel.app/api/top-langs/?username=Crud-Make&layout=compact&theme=tokyonight&locale=pt-br&hide_border=true)

</div>
