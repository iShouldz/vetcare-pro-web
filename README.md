# VETCAREPRO

Front-end web do VetCarePro, uma plataforma para gestão de clínicas veterinárias com foco em operação diária: atendimento, agenda, cadastro, equipe, finanças e vendas.

## Qualidade de código

[![Codacy Badge](https://app.codacy.com/project/badge/Grade/744123118cf94c6c83aac3491a6dc8df)](https://app.codacy.com/gh/iShouldz/toDeploy/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)

## Visão geral do produto

O VetCarePro organiza o fluxo da clínica em módulos conectados:

- **Acesso e onboarding** (login, cadastro, tour guiado)
- **Gestão de clínicas** (listagem, criação, edição e exclusão)
- **Gestão clínica interna** (pacientes, serviços, funcionários e agendamentos)
- **Painel operacional** com visão de consultas próximas, busca e ações rápidas
- **Planos de assinatura** com recursos por nível
- **Gestão de produtos e vendas** com carrinho e checkout
- **Painel financeiro** com receitas, débitos e pagamentos

## Rotas principais

- Públicas: `/home`, `/pricing`, `/team`, `/adoption`, `/login`
- Dashboard geral: `/dashboard/listagemClinica`
- Área interna da clínica: `/internalClinica/:idClinica/...`
  - `/dashboard`
  - `/listagemPaciente`, `/cadastrarPaciente`, `/detailsPaciente/:id`
  - `/listagemServico`, `/cadastrarServico`, `/detailsServico/:id`
  - `/listagemFuncionario`, `/cadastrarFuncionario`
  - `/listagemAgendamento`, `/agendamento`
  - `/listagemProdutos`
  - `/dashboardFinanceiro`

## Integrações externas

- API própria via `VITE_URL` (autenticação, cadastros, agenda, finanças, vendas etc.).
- WhatsApp (abertura de conversa para contato com tutor).
- PIX via geração de QR Code.
- EmailJS para envio de e-mail em fluxo de cadastro.
- Links externos de LinkedIn/GitHub na página de time.

## Requisitos e execução

- Node.js 20+
- npm

```bash
npm install
npm run dev
```

## Scripts

- `npm run dev` — ambiente de desenvolvimento
- `npm run lint` — validação estática com ESLint
- `npm run build` — build de produção

