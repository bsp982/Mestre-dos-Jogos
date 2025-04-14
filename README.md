# 🧩 Mestre dos Jogos

**Mestre dos Jogos** é uma plataforma web de aluguel de jogos de tabuleiro, desenvolvida com Angular 18 no frontend e Node.js 20 no backend.

## 👥 Perfis de Usuário

- **Cliente**
  - Visualiza o catálogo de jogos
  - Realiza aluguéis com data de retirada e devolução
  - Efetua pagamento online
  - Acompanha seus pedidos

- **Gestor**
  - Cadastra/edita jogos
  - Acompanha aluguéis ativos e finalizados
  - Visualiza métricas em um dashboard de gestão

---

## 🧱 Tecnologias Utilizadas

| Camada         | Tecnologia                               |
|----------------|-------------------------------------------|
| Frontend       | Angular 18 (standalone)                   |
| Estilo         | Angular Material / Tailwind CSS           |
| Backend        | Node.js 20 + Express                      |
| ORM            | Prisma                                    |
| Banco de Dados | PostgreSQL (ou MongoDB, configurável)     |
| Autenticação   | JWT                                       |
| Pagamentos     | Stripe ou Pagar.me                        |

---

## ⚙️ Estrutura do Projeto

```bash
mestre-dos-jogos/
├── frontend/        # Aplicação Angular
├── backend/         # API Node.js + Express
├── README.md
└── ...
