# VETCAREPRO

Front-end web do VetCarePro, uma plataforma para gestão de clínicas veterinárias com foco em operação diária: atendimento, agenda, cadastro, equipe, finanças e vendas.

## Integrantes

[Weverton Cintra](https://github.com/WevertonCintra) | [Pedro Souza](https://github.com/iShouldz) | [Luiz Fellipe](https://github.com/Luizfdarb) | [Lucas Romeiro](https://github.com/lucas-romeiro) | [Romário Abílio](https://github.com/romarioabilio)

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

## Funcionalidades principais

### 1) Área pública e apresentação

- Página inicial com proposta de valor, seção de recursos, depoimentos e CTA para planos.
- Página de **preços/assinatura** com comparação entre Free, Standard e Enterprise.
- Página de **time** com links para perfis sociais.
- Página de **adoção** com cards de animais disponíveis.

### 2) Acesso e conta

- Cadastro de usuário com validação de formulário.
- Login com opção de “continuar logado”.
- Perfil com dados da conta e ações rápidas (logout, reabrir tutorial).
- Tema escuro/claro e customização visual do header.

### 3) Gestão de clínicas

- Listagem de clínicas com paginação.
- Criação, edição e remoção de clínicas (de acordo com perfil de acesso).
- Entrada na área interna de cada clínica.

### 4) Módulos internos da clínica

- **Pacientes:** cadastro, listagem paginada, edição, detalhes e histórico clínico.
- **Serviços:** cadastro, listagem paginada, edição e detalhes.
- **Funcionários:** cadastro, listagem paginada, edição, exclusão e controle de folha.
- **Agendamentos:** criação, edição, listagem paginada e conclusão de consulta.

### 5) Dashboard da clínica

- Cards de visão geral (total de pacientes, próximas consultas e lucro).
- Busca de consultas e serviços por texto.
- Paginação configurável nas tabelas.
- Ações rápidas por consulta (mensagem via WhatsApp, pagamento via PIX, concluir).

### 6) Produtos e vendas

- Cadastro/edição de produtos.
- Listagem de produtos com status de estoque (incluindo “esgotado”).
- Carrinho com ajuste de quantidade, total e fechamento de compra.
- Fluxo de pagamento com QR Code PIX.

### 7) Painel financeiro

- Indicadores financeiros (vendas, consultas, valor a receber, receita total, débito salarial).
- Controle de visibilidade dos valores.
- Pagamento de funcionários com validações de saldo e periodicidade.
- Cadastro/atualização de chave PIX para recebimentos.

### 8) Experiência de uso

- Layout responsivo com variações de grid para mobile/tablet/desktop.
- Breadcrumbs e navegação lateral na área interna.
- Estados de carregamento com skeleton/loading.
- Tratamento básico de erro com mensagens em tela.
- Estado vazio em pontos críticos (ex.: nenhum produto encontrado).
- Notificações in-app para ações do usuário.

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

## Internacionalização

- A interface está predominantemente em **português**.
- Não há, no estado atual, um mecanismo completo de troca de idioma em runtime.

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

## Convenção de commits

- `feat` — novas funcionalidades
- `fix` — correções de bug
- `refactor` — refatorações sem mudança de comportamento final
- `chore` — tarefas internas e manutenção
- `docs` — documentação
- `perf` — melhorias de performance
- `style` — ajustes de estilo/formatação
- `test` — testes
- `build` — build/dependências
- `ci` — integração contínua
- `env` — configurações de ambiente/infra
