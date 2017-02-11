#Simple Flyway Exercise

The point of this project is to try out [Flyway](https://flywaydb.org/) database migrations, some of the exercise I will be creating will try edge cases/ cause errors.

To change which set of migrations run go into application.properties and change the flyway.locations to db/migration{d} where d is the migration number or left off completely for the very basic migration example

####Example 1
db/migration - most basic example, only migration is run

####Example 2
db/migration2 - a very basic example with two migrations

####Example 3
db/migration3 - slightly malformed example migration skips V2__{descriptions}.sql, still works. It worth running
```SQL
SELECT * FROM "schema_version"
```

in the h2 web console and look at the resulting table.

####Example 4
Simple example with a subversion migration.