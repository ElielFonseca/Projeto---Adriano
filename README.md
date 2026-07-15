# Agenda Barbearia

App web para barbearias: o dono cadastra a loja, define dias e horários disponíveis, e os clientes agendam online. Cada horário marcado fica indisponível automaticamente.

## Stack

- Next.js 15 (App Router) + TypeScript + Tailwind
- Prisma + SQLite
- Autenticação do dono com sessão (JWT em cookie)

## Como rodar

```bash
cd frontend
npm install
npx prisma migrate dev
npm run dev
```

Abra [http://localhost:3000](http://localhost:3000).

## Fluxo

1. **Dono** cria conta em `/register`
2. Cadastra a barbearia em `/dashboard/barbershop` (gera o link `/b/seu-slug`)
3. Define dias e horários em `/dashboard/availability`
4. **Cliente** abre o link público, escolhe dia/horário e confirma com nome e telefone
5. O agendamento aparece no painel `/dashboard` e o horário some da agenda

## Variáveis de ambiente

Arquivo `frontend/.env`:

```
DATABASE_URL="file:./dev.db"
AUTH_SECRET="troque-em-producao"
```
