# Seeding:
## Introduction:
Seerers are the demo data for database tables. Seeders are used to manage all dtaa migrations. Seed files are some changes in data that can be used to populate database tables with sample or test data.

# How to Create Seed file
let's create a seed file for our user table that will add demo data to it.
``` npx seqeulize-cli seed:generate --name demo-user ```
This command will create a seed file in ```seeders``` folder. File name will look something like ```XXXXXXXXXXXXXX-demo-user.js.``` It follows the same ```up / down``` semantics as the migration files.

Now we should edit file to insert demo user to ``` User ``` table
````
```
module.exports = {
  up: (queryInterface, Sequelize) => {
    return queryInterface.bulkInsert('Users', [{
      firstName: 'John',
      lastName: 'Doe',
      email: 'example@example.com',
      createdAt: new Date(),
      updatedAt: new Date()
    }]);
  },
  down: (queryInterface, Sequelize) => {
    return queryInterface.bulkDelete('Users', null, {});
  }
}
```
````

# Running a seed

in last step we have created a seed file, but it has been commited the database. To run a seed, we use the command:
``` npx sequelize-cli db:seed:all ```

This will execute that seed file and a demo user will be inserted into the User table.

# Note
Seeder execution history is not stored anywhere, unlike migrations, which use the ```SequelizeMeta``` table. If you wish to change this behavior, please read the ```Storage``` section.