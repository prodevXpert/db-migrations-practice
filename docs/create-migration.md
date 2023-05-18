# Creating migration
This will use ``` model:generate ``` command which requires two options.
1. ``` name: ``` The model name.
2. ``` attributes: ``` the list of model attributes.

## Here is the example to creating the migration.
``` npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,email:string ```

### This will:
1. Create a model file user in models folder;
2. Create a migration file with name like XXXXXXXXXXXXXX-create-user.js in migrations folder.

# Note:
Sequelize will only use Model files, it's the table representation. On the other hand, the migration file is a change in that model or more specifically that table, used by CLI. Treat migrations like a commit or a log for some change in database.

# Running Migrations
Until this step, we haven't inserted anything into the database. We have just created the required model and migration files for our first model, User. Now to actually create that table in the database you need to run db:migrate command.

``` npx sequelize-cli db:migrate ```

This command will execute these steps:

1. Will ensure a table called ``` SequelizeMeta ``` in database. This table is used to record which migrations have run on the current database
2. Start looking for any migration files which haven't run yet. This is possible by checking ``` SequelizeMeta ``` table. In this case it will run ``` XXXXXXXXXXXXXX-create-user.js ``` migration, which we created in last step.
3. Creates a table called ``` Users ``` with all columns as specified in its migration file.