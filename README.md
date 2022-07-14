# Try Supabase development

## Local dev

**Setup**

- Docker
- Supabase CLI
- Deno CLI

**Run project**

1. On root repo, execute:

```sh
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

### Database migrations

**Preview changes**

```sh
supabase db changes
```

**Seeds data**

1. Add seed INSERT statement in [supabase/seed.sql](./supabase/seed.sql).
2. Rerun migration and seed scripts `supabase db reset`.

### Develop Edge Function

- Install Deno CLI & [setup dev env](https://deno.land/manual/getting_started/setup_your_environment)
- [Tutorial](https://blog.logrocket.com/using-edge-functions-supabase-complete-guide/)
- New function: `supabase functions new <func-name>`
- Run function locally: `supabase functions serve <func-name>`
- [Deno development](https://deno.land/manual)

## Deploy

### Push database change

1. Preview changes: `supabase db push [--dry-run]`
2. Push changes: `supabase db push`

### Deploy functions

```sh
supabase functions deploy <func-name>
```
