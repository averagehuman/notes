
A Role is an entity that can own database objects and be assigned database privileges.

A LOGIN Role is a Role that can be used to initiate a client session.

`CREATE ROLE ...` will create a non-LOGIN Role by default.

`CREATE ROLE LOGIN ...` will create a LOGIN Role.

`CREATE USER ...` is just an alias for `CREATE ROLE LOGIN ...`.

Roles and Users are sometimes used interchangeably, but lets say 'User == Login Role'

Use `INHERIT` to allow a Role to automatically be assigned the privileges of other roles
to which it belongs.


Users
-----

Create a User::

    CREATE ROLE "bob" LOGIN PASSWORD 'mysecret' INHERIT;


Update a user password::

    ALTER ROLE "bob" WITH PASSWORD 'newsecret';


