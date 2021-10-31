# Solana NFT Bot

Solana NFT bot is a helpful bot for your Solana NFT projects.

## Features
- [x] Notify discord channel on each purchase in marketplaces. 
- [x] [Support major marketplaces](#marketplace-support) 

## Running in development
### Requirement
* Node >= 16.6
* Yarn

### Instructions

#### 1. Install dependencies
```
yarn install
```

#### 2. Update .env with your secrets

Follow the instructions [here](#configurable-environments)

#### 3. Run the server 
```
yarn dev
```

## Running using docker

### Requirement
* [docker](https://www.docker.com/products/docker-desktop) >= v20.10

### Instructions

#### 1. Update .env with your secrets

Follow the instructions [here](#configurable-environments)

#### 2. Run bot using docker compose in the terminal
In the terminal run the follow command in the repo directory:

```
docker-compose up bot
```

## Configurable environments

Here are a list of environments you need to configure before running the NFT bot.

```sh
# Replace this with your RPC
SOLANA_RPC=https://explorer-api.mainnet-beta.solana.com/
# Discord bot secret
DISCORD_BOT_TOKEN=
# The discord channel to notify
SUBSCRIPTION_DISCORD_CHANNEL_ID=
# Mint address to watch for sales
SUBSCRIPTION_MINT_ADDRESS=
```
https://github.com/milktoastlab/SolanaNFTBot/blob/main/.env

### Variable breakdowns

#### DISCORD_BOT_TOKEN
This is your discord bot secret.
If you don't have a discord bot yet, you can create one following the instructions here:
https://discordpy.readthedocs.io/en/stable/discord.html

Make sure your bot has the required permissions:
* View channels
* Read/Send messages
* Send messages
* Embed links

<img width="827" alt="Screen Shot 2021-10-31 at 9 25 31 am" src="https://user-images.githubusercontent.com/90617759/139560537-e0420217-25d7-4538-81cc-d53422c24db9.png">

#### SUBSCRIPTION_DISCORD_CHANNEL_ID
This is the ID of the discord channel you want to send notifications to.
You will need to enable developer mode have access the channel IDs.
Here are the instructions:
https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID-

#### SUBSCRIPTION_MINT_ADDRESS
This is the address that you want the Solana NFT bot to watch for notifications.
Ideally, it's the "Update Authority" address.

<img width="587" alt="Screen Shot 2021-10-31 at 9 30 56 am" src="https://user-images.githubusercontent.com/90617759/139560515-efd2f584-8f98-4337-a9ad-704b18581b22.png">


## Marketplace support

- [x] [Magic Eden](https://magiceden.io/)
- [x] [Solanart](http://solanart.io/)
- [x] [Digital Eyes](https://digitaleyes.market/)
- [ ] [Solsea](https://solsea.io/)
- [ ] [Alpha Art](https://alpha.art/)

### Adding new marketplace

SolanaNFTBot aim to support as many marketplaces are possible. 
Here is the instruction on how you can add support to other marketplaces.

#### 1. Add a new marketplace config
Use `src/lib/marketplaces/digitalEyes.ts` as example

#### 2. Get write a test for the marketplace
Use `src/lib/marketplaces/digitalEyes.test.ts` as example

#### 3. Add the new marketplace to the existing list 
`src/lib/marketplaces/marketplaces.ts`

