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

####Example 5
Two migrations evaluate to version 2. An error occurred as should be expected. Fairly good error message also
```
org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'flywayInitializer' defined in class path resource [org/springframework/boot/autoconfigure/flyway/FlywayAutoConfiguration$FlywayConfiguration.class]: Invocation of init method failed; nested exception is org.flywaydb.core.api.FlywayException: Found more than one migration with version 2
Offenders:
-> {locationOfProject}/flyway/target/classes/db/migration5/V2__roles.sql (SQL)
-> {locationOfProject}/flyway/target/classes/db/migration5/V2_0__alter_roles.sql (SQL)
```