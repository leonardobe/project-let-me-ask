# NLW Agents

Projeto desenvolvido durante o evento **NLW-Agents** da [Rocketseat](https://rocketseat.com.br/) com o objetivo de integrar um frontend moderno com uma API robusta baseada em agentes inteligentes.

---

## 🧩 Estrutura do Repositório

```
nlw-agents/
├── web/     → Frontend (React + Vite)
├── server/  → Backend (Fastify + PostgreSQL)
└── README.md
```

---

## 🚀 Tecnologias

### 🔹 Backend (Server)
- **Node.js** com TypeScript (experimental strip types)
- **Fastify** – framework web leve e rápido
- **PostgreSQL** com extensão **pgvector**
- **Drizzle ORM** – queries type-safe
- **Zod** – validação de schemas
- **Docker** – banco de dados isolado
- **Biome** – linting e formatação

### 🔸 Frontend (Web)
- **React 19.1** com TypeScript 5.8
- **Vite 7.0** – build rápido e dev server
- **TailwindCSS 4.1** – utilitários CSS
- **TanStack React Query** – gerenciamento de estado do servidor
- **React Router Dom** – roteamento SPA
- **Radix UI + Shadcn/ui** – componentes acessíveis e estilizados
- **Lucide React** – ícones modernos

---

## ⚙️ Instalação e Uso

### 🛠️ Pré-requisitos

- Node.js 18+
- Docker e Docker Compose
- npm ou yarn

---

### 🔧 Backend (`/server`)

1. Acesse a pasta do servidor:
   ```bash
   cd server
   ```

2. Inicie o banco com Docker:
   ```bash
   docker-compose up -d
   ```

3. Crie um arquivo `.env` com o conteúdo:
   ```env
   PORT=3333
   DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
   GEMINI_API_KEY="SUA CHAVE API"
   ```

4. Instale as dependências:
   ```bash
   npm install
   ```

5. Rode as migrações:
   ```bash
   npx drizzle-kit migrate
   ```

6. (Opcional) Popule o banco:
   ```bash
   npm run db:seed
   ```

7. Inicie o servidor:
   ```bash
   npm run dev
   ```
> [!IMPORTANT]
> API disponível em: `http://localhost:3333`

---

### 🌐 Frontend (`/web`)

1. Acesse a pasta do frontend:
   ```bash
   cd web
   ```

2. Instale as dependências:
   ```bash
   npm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   npm run dev
   ```
> [!IMPORTANT]
> Aplicação disponível em: `http://localhost:5173`

---

## 🛠️ Estrutura de Pastas

### Frontend (`/web`)
```
src/
├── 📂 components/ui/    # Componentes visuais reutilizáveis
├── 📂 pages/            # Páginas da aplicação
├── 📂 lib/              # Utilitários e integrações
└── 📄 app.tsx           # Componente raiz
```

### Backend (`/server`)
```
src/
├── 📂 db/
│   ├── 📂 migrations/        # Migrações SQL
│   │   └── 📂 meta/          # Metadados de migração
│   ├── 📂 schema/            # Schemas do banco (Drizzle)
│   ├── 📄connection.ts       # Conexão com banco
│   └── 📄 seed.ts            # Seed de dados
├── 📂 http/
│   └── 📂 routes/            # Arquivos de rota da API
├── 📂 services/
│   └── 📄 gemini.ts          # Integração com API gemini
│
├── 📄 env.ts                 # Validação de variáveis de ambiente
└── 📄 server.ts              # Arquivo principal do servidor
```

---

## 🌐 Endpoints da API

- `GET /health` – Verifica status da API
- `GET /rooms` – Lista salas disponíveis
- `POST /rooms` – Cria uma nova sala
- `POST /questions` – Cria uma nova pergunta

> [!IMPORTANT]
> Todos os endpoints devem ser testados com a API rodando em `http://localhost:3333`

---

## 🔁 Scripts Disponíveis

### Backend
- `npm run dev` – Modo desenvolvimento
- `npm start` – Modo produção
- `npm run db:seed` – Popula o banco

### Frontend
- `npm run dev` – Inicia frontend em modo dev
- `npm run build` – Gera build de produção
- `npm run preview` – Testa build localmente

---

## 🧪 Testes com REST Client

Você pode testar a API usando o arquivo [`client.http`](server/client.http) com a extensão [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) no VS Code.

---

## 📚 Créditos

Desenvolvido com 💜 durante o evento NLW da Rocketseat por [Leonardo Curtis]([https://github.com/seuusuario](https://github.com/leonardobe))
