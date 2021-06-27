# yt-subscribers-list

## Dev Setup

Basic Instructions to get the backend setup, this requires Docker (alternatively you can install Postgres locally).

**Database (& Tools) via Docker**

The below command sets up a container with the Postgres Database which will run at `postgres://localhost`

```bash
# bash
$ docker run -d \
   --name=postgresDev \
   -e POSTGRES_DB=ytSubscribersList \
   -e POSTGRES_USER=ytSubscribersList \
   -e POSTGRES_PASSWORD=ytSubscribersList \
   -p 5432:5432 \
   postgres

# powershell
$ docker run -d `
   --name=postgresDev `
   -e POSTGRES_DB=ytSubscribersList `
   -e POSTGRES_USER=ytSubscribersList `
   -e POSTGRES_PASSWORD=ytSubscribersList `
   -p 5432:5432 `
   postgres
```

The below command sets up a container with the Postgres PG Admin Tools which will run at `http://localhost`

```bash
# bash
$ docker run -d \
   --name=postgresAdmin \
   -e PGADMIN_DEFAULT_EMAIL=chris@talke.dev \
   -e PGADMIN_DEFAULT_PASSWORD=ytSubscribersList \
   -p 80:80 \
   dpage/pgadmin4

# powershell
$ docker run -d \
   --name=postgres_admin `
   -e PGADMIN_DEFAULT_EMAIL=chris@talke.dev `
   -e PGADMIN_DEFAULT_PASSWORD=ytSubscribersList `
   -p 80:80 `
   dpage/pgadmin4
```

**Backend Setup**

```bash
# bash && powershell
$ cd /app
$ npx keystone create-tables
$ npm run dev
```
