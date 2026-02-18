# Deploying

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
