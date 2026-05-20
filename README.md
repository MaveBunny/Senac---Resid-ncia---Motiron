# **Senac Motiron**

## **Descrição:**
O Senac Motiron é uma solução web moderna criada para centralizar a divulgação e gestão de todas as atividades acadêmicas da instituição, como palestras, workshops e conferências. O sistema elimina a dispersão de informações, permitindo que alunos e o público externo encontrem e se inscrevam em eventos em um só lugar, com uma interface intuitiva e premium.

**Tecnologias Usadas**
- React 19
- Next.js 15 (App Router) — framework fullstack
- TypeScript
- Tailwind CSS v4
- shadcn/ui — componentes de interface
- Framer Motion — animações
- Lucide React — ícones
- Supabase / PostgreSQL - Banco de dados e persistência

## **Arquitetura**
O projeto utiliza o App Router do Next.js, aproveitando o poder das rotas de API integradas e a navegação client-side otimizada.

Estrutura principal:

senac-motiron/
├── src/
│   ├── app/                 # Core da Aplicação (App Router)
│   │   ├── api/             # Endpoints Backend (Next.js API Routes)
│   │   │   ├── auth/        # Lógica de login e registro (route.ts)
│   │   │   ├── events/      # CRUD de atividades e cancelamento (route.ts)
│   │   │   └── registrations/# Controle de inscrições e presenças (route.ts)
│   │   ├── dashboard/       # Painel administrativo do gestor (page.tsx)
│   │   ├── login/           # Tela de autenticação (page.tsx)
│   │   ├── register/        # Tela de cadastro de novos usuários (page.tsx)
│   │   ├── atividades/      # Catálogo e Detalhes de eventos (page.tsx)
│   │   ├── agenda/          # Controle de atividades do aluno (page.tsx)
│   │   ├── layout.tsx       # Template global, fontes e metadados
│   │   └── page.tsx         # Landing Page / Home
│   ├── components/          # Componentes de UI e Interface
│   │   └── ui/              # Componentes base (Button, Card, Input, etc)
│   ├── data/                # Serviços de dados e interfaces (events.ts)
│   ├── lib/                 # Configurações de libs (utils.ts)
│   └── utils/               # Helpers globais (auth.ts)
├── public/                  # Ativos estáticos (imagens, ícones)
├── database.sql             # Script de criação do banco de dados (Tabelas em singular: usuario, evento, inscricao)
└── package.json             # Dependências e scripts do projeto

## **Fluxo de Navegação**
Rota	Página	Acesso
/	Landing Page informativa	Público
/atividades	Catálogo completo de eventos com busca e filtros	Público
/login	Tela de acesso ao sistema	Público
/agenda	Agenda personalizada com eventos inscritos	Aluno
/dashboard	Cockpit de gestão (Métricas, Eventos, Inscritos, Cadastro)	Gestor
Autenticação e Segurança
A autenticação é gerenciada via persistência em localStorage com controle de estado centralizado no utilitário src/utils/auth.ts.

Nível de Acesso: O sistema diferencia aluno e gestor, protegendo rotas administrativas.
Saudação Personalizada: O sistema recupera o nome real do usuário para uma experiência personalizada.
Credenciais de teste sugeridas: (Conforme configurado no banco de dados)

Tipo	Matrícula	Senha
Gestor	gestor	1234
Aluno	aluno	1234

## **instruções para execução**
Rodando localmente
Requisitos: Node.js v20+ e um banco de dados PostgreSQL.

## **Clone o repositório:**

git clone https://github.com/gbarros/senac-motiron.git
cd senac-motiron
Configure o banco de dados:

Execute o script database.sql no seu servidor PostgreSQL (ou Supabase).
Crie um arquivo .env.local na raiz do projeto seguindo o modelo:
DATABASE_URL="postgresql://usuario:senha@host:5432/banco"
OBS: O arquivo.env.local é onde esta as informacoes do banco de dados
Instale as dependências:

npm install
Inicie o servidor de desenvolvimento:

npm run dev
Acesse no navegador: http://localhost:3000

## **Design System**
O projeto utiliza um design system personalizado baseado nas cores institucionais do Senac, com foco em:

Acessibilidade: Contrastes validados e fontes legíveis.
Responsividade: Layout adaptável para dispositivos móveis e desktop.
Aesthetics: Uso de micro-interações, sombras suaves e gradientes modernos.
