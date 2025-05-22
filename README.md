<div align="center">
<img src="https://static.wikitide.net/hexagonwiki/thumb/7/70/HexagonLogo.png/600px-HexagonLogo.png" alt="Btwaf " width="300"/>
</div>

<h1 align="center">Hexagon</h1>

<div align="center">

[![SvelteKit](https://img.shields.io/badge/SvelteKit-2.21.1-orange?logo=svelte)](https://github.com/SkylerClock/Hexagon)
[![Docker](https://img.shields.io/badge/Docker-28.1.1-blue?logo=docker)](https://github.com/SkylerClock/Hexagon)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-yellow?logo=typescript)](https://github.com/SkylerClock/Hexagon)
[![Node.js](https://img.shields.io/badge/Node.JS-24.1.0-green?logo=nodedotjs)](https://github.com/SkylerClock/Hexagon)
[![Sushi](https://img.shields.io/badge/Developer-SushiDesigner-white)](https://github.com/SushiDesigner)
[![Shikataganaii](https://img.shields.io/badge/Leaked_By-Chloe/Shikataganaii-white)](https://github.com/shikataganaii)

Hexagon is a popular 2013/2014 Roblox Revival (Credits to Chloe/Shikataganaii for leaking this)
</div>

# WARNING

Please do not re-host this to the public. we know it is a source code that can start your own revival but re-hosting is unrecommended for reasons.
This repository is only created for testing out or understanding the logic of SvelteKit and Node made revivals and how they work.
If you want to build your own roblox please use https://github.com/tp-link-extender/MercuryCore instead.

# HOW TO SETUP

To setup/host hexagon you'll need the following dependencies:
- Node JS
- Docker Desktop
- Go/Golang (latest version is recommended)
- Postgresql (16 or above is recommended)

1. Rename .env.example to .env and put your database info there or other things like discord webhook.

```shell
DEBUG=true/false # (false for production build and true for debug build)
DATABASE_URL="postgres://username:password@postgrsipandport/databasename" # (postgres credentials here)
DATABASE_LOGS=false
DISCORD_CLIENT_ID="123"
DISCORD_CLIENT_SECRET=""
DISCORD_REDIRECT_URI=""
DISCORD_LINKENABLED=true
DISCORD_WEBHOOK_STATS=""
BASE_URL="hexagon.pw" # (change this to your base url)
CLOUDFLARE_S3_ACCOUNT_ID=""
CLOUDFLARE_S3_ACCESS_KEY_ID=""
CLOUDFLARE_S3_ACCESS_KEY=""
# NOTE CLOUDFLARE IS JUST WHAT I USED ANY S3 COMPATIBLE SERVICE WILL DO
# in addition check stores.ts for extra config stuffs
GAMESERVER_IP="" # (gameserver ip here)
ARBITER_HOST="ip:port" # (arbiter ip and port here)
RENDER_HOST="ip:port" # (render ip and port here)
RCC_ACCESS_KEY="" # you set this in the registry make sure it matches or your stats wont work / games
ASSET_ACCESS_KEY=""
JWT_SECRET_KEY="" # used for tickets not for auth
EVICT_KEY=""
CLIENT_PRIVATE_KEY="-----BEGIN RSA PRIVATE KEY-----

-----END RSA PRIVATE KEY-----" # (change to your private key)
PUBLIC_setupcdn="setup.hexagon.pw" # (change to your setup url)
BODY_SIZE_LIMIT=Infinity
PUBLIC_ANALYTICS=false
PUBLIC_ANALYTICS_WEBSITEID=""
PUBLIC_DISCORD_INVITE=""
DISABLE_RENDER=false
```

2. Launch Docker Desktop and start Docker (this will allow you to use docker's containers)

3. Compiling Time! For a Developer environment
Run the following commands
```shell
docker compose -f compose_dev.yml build
```
```shell
docker compose -f compose_dev.yml up
```
For a Production environment run the following commands (please note that you need to setup the hexagon-maintenance project for caddy's error pages)
```shell
docker compose build
```
```shell
docker compose up -d
```

If everything was successful try going to localhost:3000 and if you see the sign up page congratulations you have setup hexagon's web environment

# Extra Note
Please note that you have to make your own arbiter because hexagon's own RUST-based arbiter is not available out there (and won't likely be available anytime soon) Plus you'd have to recreate the entire database structure in order for this to work correctly with no issues.
