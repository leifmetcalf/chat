```
export MIX_ENV=prod
mix deps.get
mix compile
mix assets.deploy
mix release
sudo
  SECRET_KEY_BASE=$(mix phx.gen.secret)
  DATABASE_URL=ecto://postgres@localhost/chat_app_prod
  NOATS_SSL_KEY_PATH=/etc/letsencrypt/live/noats.nz/privkey.pem
  NOATS_SSL_CERT_PATH=/etc/letsencrypt/live/noats.nz/fullchain.pem
  _build/prod/rel/chat_app/bin/server
```
