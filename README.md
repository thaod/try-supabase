# Try Supabase development

## Local dev

**Setup**

- Docker
- Supabase CLI

**Run project**

1. On root repo, execute:

```bash
supabase start
```

Supabase will setup Docker containers. When finish, Supabase access info will be printed to console. With `docker ps`, you will see containers running as below screenshot.

![](./docs/assets/supabase_start.png)

2. Access:

- Postgres URL: `postgresql://postgres:postgres@localhost:54322/postgres`
- Supabase Studio: http://localhost:54323
- API URL: http://localhost:54321

3. Editor:

- Use any SQL client connect to Postgres URL.
- Or edit directly on [Supabase Studio](http://localhost:54323).

SQL client suggestions:

- [SQLTools on VS Code](https://vscode-sqltools.mteixeira.dev/)
- [DBeaver](https://dbeaver.io/)

4. Commit changes to create database migration

After any update, execute `supabase db commit <change_name>` to create migration.

## Development guide

## Deploy

### Database migrations

### Deploy Supabase Edge Functions

```bash
supabase functions deploy <function_name>
```
