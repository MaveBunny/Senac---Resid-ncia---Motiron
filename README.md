# Senac Motiron

Sistema web moderno desenvolvido para centralizar a divulgação, inscrição e gestão de atividades acadêmicas do Senac, como palestras, workshops, conferências e demais eventos institucionais.

O **Senac Motiron** busca resolver a dispersão de informações sobre eventos acadêmicos, oferecendo uma plataforma única, intuitiva e responsiva para alunos, gestores e público externo.

---

## Sobre o Projeto

O Senac Motiron é uma solução fullstack construída com **Next.js**, **React**, **TypeScript** e **Supabase/PostgreSQL**, com foco em usabilidade, organização institucional e experiência premium.

A plataforma permite que usuários encontrem eventos, realizem inscrições e acompanhem sua agenda personalizada. Já os gestores têm acesso a um painel administrativo para cadastrar, editar, cancelar e acompanhar atividades e inscrições.

---

## Funcionalidades

### Público geral

- Visualização da landing page institucional
- Acesso ao catálogo de atividades
- Busca e filtros de eventos
- Cadastro e login no sistema

### Aluno

- Inscrição em eventos
- Visualização da agenda personalizada
- Acompanhamento das atividades inscritas
- Experiência personalizada com saudação pelo nome

### Gestor

- Acesso ao dashboard administrativo
- Cadastro de novas atividades
- Edição de eventos
- Cancelamento de atividades
- Visualização de métricas
- Controle de inscritos e presenças

---

## Tecnologias Utilizadas

- React 19
- Next.js 15 com App Router
- TypeScript
- Tailwind CSS v4
- shadcn/ui
- Framer Motion
- Lucide React
- Supabase
- PostgreSQL

---

## Arquitetura do Projeto

O projeto utiliza o **App Router do Next.js**, aproveitando rotas integradas de API, navegação otimizada e organização modular.

```bash
senac-motiron/
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   ├── auth/
│   │   │   ├── events/
│   │   │   └── registrations/
│   │   ├── dashboard/
│   │   ├── login/
│   │   ├── register/
│   │   ├── atividades/
│   │   ├── agenda/
│   │   ├── layout.tsx
│   │   └── page.tsx
│   ├── components/
│   │   └── ui/
│   ├── data/
│   ├── lib/
│   └── utils/
├── public/
├── database.sql
└── package.json

| Rota          | Página                       | Acesso  |
| ------------- | ---------------------------- | ------- |
| /           | Landing Page informativa     | Público |
| /atividades | Catálogo completo de eventos | Público |
| /login      | Tela de autenticação         | Público |
| /agenda     | Agenda personalizada         | Aluno   |
| /dashboard  | Painel administrativo        | Gestor  |




Autenticação e Segurança
A autenticação é gerenciada via persistência em localStorage com controle de estado centralizado no utilitário src/utils/auth.ts.

Nível de Acesso: O sistema diferencia aluno e gestor, protegendo rotas administrativas.
Saudação Personalizada: O sistema recupera o nome real do usuário para uma experiência personalizada.
Credenciais de teste sugeridas: (Conforme configurado no banco de dados)

| Tipo de Usuário | Matrícula | Senha  |
| --------------- | --------- | ------ |
| Gestor          | gestor  | 1234 |
| Aluno           | aluno   | 1234 |

Instruções para execução
Rodando localmente
Requisitos: Node.js v20+ e um banco de dados PostgreSQL.

1.Clone o repositório:
git clone https://github.com/gbarros/senac-motiron.git
cd senac-motiron

2.Configure o banco de dados:
Execute o script database.sql no seu servidor PostgreSQL (ou Supabase).
Crie um arquivo .env.local na raiz do projeto seguindo o modelo:
DATABASE_URL="postgresql://usuario:senha@host:5432/banco"

OBS: O arquivo.env.local é onde esta as informacoes do banco de dados

3.Instale as dependências:
npm install

4.Inicie o servidor de desenvolvimento:
npm run dev

5.Acesse no navegador: http://localhost:3000

Design System
O projeto utiliza um design system personalizado baseado nas cores institucionais do Senac, com foco em:

Acessibilidade: Contrastes validados e fontes legíveis.
Responsividade: Layout adaptável para dispositivos móveis e desktop.
Aesthetics: Uso de micro-interações, sombras suaves e gradientes modernos.



