# DevLink

> Projeto desenvolvido como parte do curso **FullStack Pro** do [Sujeito Programador](https://sujeitoprogramador.com/), acompanhado como aluno.

Uma aplicação de gerenciamento de links pessoais (estilo Linktree), onde o usuário administrador pode cadastrar links customizados e links de redes sociais que são exibidos em uma página pública.

## Funcionalidades

- **Página pública** — exibe todos os links cadastrados com cores personalizadas e atalhos para redes sociais (Facebook, Instagram e YouTube)
- **Painel administrativo** — adiciona e remove links com nome, URL, cor do texto e cor de fundo customizáveis, com preview em tempo real
- **Gerenciamento de redes sociais** — salva e atualiza os links das redes sociais exibidos na página pública
- **Autenticação** — login via e-mail e senha protegendo todas as rotas administrativas

## Tecnologias

- [React 19](https://react.dev/) com [TypeScript](https://www.typescriptlang.org/)
- [Vite](https://vite.dev/) como bundler
- [Tailwind CSS v4](https://tailwindcss.com/) para estilização
- [Firebase](https://firebase.google.com/) — Firestore (banco de dados) e Authentication
- [React Router v7](https://reactrouter.com/)
- [React Icons](https://react-icons.github.io/react-icons/)

## Estrutura de rotas

| Rota | Descrição | Proteção |
|---|---|---|
| `/` | Página pública com os links | Privada |
| `/login` | Tela de login | Pública |
| `/admin` | Gerenciamento de links | Privada |
| `/admin/social` | Gerenciamento de redes sociais | Privada |

## Como executar localmente

### Pré-requisitos

- Node.js 18+
- Uma conta no [Firebase](https://firebase.google.com/) com um projeto criado

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/devlink.git
cd devlink
```

### 2. Instale as dependências

```bash
npm install
```

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto com as credenciais do seu projeto Firebase:

```env
VITE_FIREBASE_API_KEY=sua_api_key
VITE_FIREBASE_AUTH_DOMAIN=seu_projeto.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=seu_projeto_id
VITE_FIREBASE_STORAGE_BUCKET=seu_projeto.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=seu_sender_id
VITE_FIREBASE_APP_ID=seu_app_id
```

### 4. Configure o Firebase

No console do Firebase:

1. Ative o **Firestore Database** e crie as collections `links` e `social`
2. Ative o **Authentication** com o provedor **E-mail/Senha** e crie um usuário administrador

### 5. Execute o projeto

```bash
npm run dev
```

Acesse `http://localhost:5173` no navegador.

## Scripts disponíveis

| Comando | Descrição |
|---|---|
| `npm run dev` | Inicia o servidor de desenvolvimento |
| `npm run build` | Gera o build de produção |
| `npm run preview` | Visualiza o build localmente |
| `npm run lint` | Executa o ESLint |
