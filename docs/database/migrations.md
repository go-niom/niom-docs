---
sidebar_position: 1
---

# Migrations
In this set of articles, you'll learn the **migration commands** of Niom. To get familiar with the migration commands, we'll create a set of blog tables and insert dummy data and will do commit and rollback to cover all the essentials of migration

### Introduction

Migrations are like version control for your database, allowing your team to define and share the application's database schema definition. If you have ever had to tell a teammate to manually add a column to their local database schema after pulling in your changes from source control, you've faced the problem that database migrations solve.

The Niom Migration (NM) tool provides simple and agnostic support for creating and manipulating tables across all of Niom's supported databases.

Typically, migrations will use a straightforward script written in migration files to create and modify database tables and columns.

### Generating Migrations
You may use the `migration create` command to generate a database migration. The new migration will be placed in your db/migrations directory. Each migration filename contains a timestamp that allows Niom to determine the order of the migrations:
```bash
$ niom migration cr posts #cr => create
```
If you would like to use a custom path for generating migration. You can -p="your-path" option with the migration create command. The given path should be relative to your application's base path.
For example:
```bash
$ niom migration cr posts -p="database/test" #-p => path
```

### Running Migrations
To run all of your outstanding migrations, execute the `migration up` niom command:
```bash
$ niom migration up
```
You can also specify the custom migration path as given below:
```bash
$ niom migration up -p="database/test" #-p => path
```

If you would like to see which migrations have run thus far, you may use the `migrate status` niom command:

```bash
$ niom migration status
```

### Rolling Back Migrations
To roll back the latest migration operation, you may use the rollback Artisan command. This command rolls back the latest migrated file.

```bash
$ niom migration down
```
You can also specify the custom migration path as given below:
```bash
$ niom migration down -p="database/test" #-p => path
```
 If you would like to rollback all migration then you specify `-a` with niom migration as below

```bash
$ niom migration down -a #-a => all
$ niom migration down -a -p="database/test"
```

### Sample Migrations 
To generate sample migrations for blog you may use the `migration cr -s` noim command.
```bash
$ niom migration cr -s
```
This command will generate following directories and files:
```
db/
┗ migrations/
  ┣ 20230216162948_categories.down.sql
  ┣ 20230216162948_categories.up.sql
  ┣ 20230216162948_comments.down.sql
  ┣ 20230216162948_comments.up.sql
  ┣ 20230216162948_posts.down.sql
  ┣ 20230216162948_posts.up.sql
  ┣ 20230216162948_users.down.sql
  ┣ 20230216162948_users.up.sql
  ┣ 20230216162949_table_alter.down.sql
  ┗ 20230216162949_table_alter.up.sql
```
If would like to create sample migrations with the insert queries you may use the following command
```bash
$ niom migration cr -s seed
```
To migrate these files you may use
```bash
$ niom migration up
```


### List of commands and their uses in a nutshell:
```bash
$ niom migration <command> <arguments>  
```
```bash
 #To create posts migration files 
$ niom migration cr posts

#This will create posts at the given path -p=
$ niom migration cr posts -p="database/test" 

#This will run migration
$ niom migration up 

#This will run migration from the given path -p=
$ niom migration up -p="database/test" 

#This will show the migration status
$ niom migration status 

#This will rollback migration
$ niom migration down

#This will rollback migration from the given path -p= 
$ niom migration down -p="database/test"

#This will rollback migration all migrations
$ niom migration down -a #-a => all

#This will rollback migration all migrations from the given path -p= 
$ niom migration down -a -p="database/test"
```