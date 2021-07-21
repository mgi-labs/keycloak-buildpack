# Scalingo Buildpack for Keycloak

Add the following to your app.json:

"buildpacks": [ { "url": "https://github.com/mgi-labs/keycloak-buildpack" } ]

Inspired by [metabase-buildpack](https://github.com/metabase/metabase-buildpack)

## How to test the build script locally

Create local folders `build` and `cache`, then just run:

> ./bin/compile build cache
