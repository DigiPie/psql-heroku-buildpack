# psql-heroku-buildpack

### Purpose
This buildpack executes a PostgreSQL script file on deployment to Heroku.

### Example use-case
You are developing a NodeJS-PostgreSQL application on Github with automatic deployment to Herokuapp whenever there is a commit to the `master` branch. You would like your `setup.sql` file to be executed each time this deployment occurs in order to reset all data (re-create and re-populate tables) in the **PostgreSQL database add-on attached to your Herokuapp project.**

### How to add this buildpack
1. Open your app project's **Settings** page.
2. Under the **Buildpacks** section, add this buildpack: `https://github.com/DigiPie/psql-heroku-buildpack`
3. Under the **Config Vars** section, [set the following config variables](https://devcenter.heroku.com/articles/config-vars):

- `DATABASE_URL` : postgres://[username]:[password]@[host address]:[port]/[database name]
- `SETUP_SQL` : [filename].sql

**Example:**

- `DATABASE_URL` : postgres://johntan:hunter21@ec4-420.compute-1.freedatabasesforyou.com:5432/studentDB
- `SETUP_SQL` : setup.sql

### More info
The `DATABASE_URL` for your **PostgreSQL database add-on** can be accessed at the **Settings > View Credentials...** section of your add-on administration page. [Find out more here](https://devcenter.heroku.com/articles/heroku-postgresql-credentials).