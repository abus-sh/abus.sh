# Deploying

Compose files are named following a certain convention. All files start with
"compose.<service name>". Compose files that are only used in development or production have ".dev"
or ".prod" appended, respectively. If a file contains sensitive data that must not be committed,
".secrets" is appended. Lastly, ".yaml" is appended.

All secret files should have a template file committed to the repository with all sensitive
information removed. The template file must have the same name as the original file with ".example"
appended to it.

The compose file for mautrix-discord requires that the `BASE_PATH` environment variable be set to 
the directory containing the `mautrix-discord` directory.

The first lauch of Continuwuity must be started differently to create an initial user. Run the
following command (replacing with the real username and password), then start it normally when it
finishes running.

```
docker compose -f compose.continuwuity.yaml run \
  --rm homeserver \
  conduwuit --execute 'users create [username] [password]' \
  --execute 'server shutdown'
```
