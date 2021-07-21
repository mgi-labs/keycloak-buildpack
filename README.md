# Scalingo Buildpack for Keycloak

Using this buildpack, you can deploy an instance of Keycloak on Scalingo, linked to a Postgres database.

Every time an app using this buildpack is deployed, the script `bin/compile` will execute and set up a local Keycloak installation in the folder `/app/target/keycloak`.

## How to use this buildpack in a Scalingo app

Add a .buildpacks file to the Scalingo app code source, with the following:

```json
https://github.com/Scalingo/buildpack-jvm-common.git
https://github.com/mgi-labs/keycloak-buildpack.git#v12.0.4
```

This instructs Scalingo to execute the JVM buildpack (sets up a Java runtime) and our custom Keycloak buildpack (downloads and sets up a Keycloak installation), every time the app is deployed.

## How to test the build script locally

Create local folders `build` and `cache`, then just run:

> ./bin/compile build cache

# Sources

This buildpack takes inspiration from the following sources:
- [metabase-buildpack](https://github.com/metabase/metabase-buildpack) (similar setup: it deploys on Scalingo a Java-based solution that is backed by a PostgreSQL database)
- [the build script for the official Keycloak docker containers](https://github.com/keycloak/keycloak-containers/blob/master/server/tools/build-keycloak.sh)
