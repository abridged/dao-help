# dao-help

Collab19: NodeRed based DAO Ops bot system.

Spin up your own Aragon DAO system inside of telegram using Abridged account contracts and an Aragon DAO framework! See Collab19 here as an example of what to anticipate: <https://t.me/collab19_bot>

The Collab19 DAO template uses [Node-Red](https://nodered.org/), an open source visual development environment. 

Web3 components include [Aragon OS](https://aragon.org) for the decentralized organization and the Abridged SDK for the Ethereum account and transactions. See the docs [here](https://abridged.gitbook.io/docs/) and find an interface for the SDK [here](https://preview.abridged.io/)

## Pre-requisites (30 mins)

1. Make sure you are running a [supported version](https://nodered.org/docs/faq/node-versions) of node.js.

2. Use [this link](https://mainnet.aragon.org/) to create a decentralized organization with Aragon. Use the "Company Template".

3. You will need an [Airtable](https://airtable.com/) account to manage the DAO userbase, and you will need to create a bot in [Telegram](https://core.telegram.org/bots).

4. An [AWS account](https://aws.amazon.com/console/) is necessary to encrypt user private keys.

## Step 1: Download Node-Red (5 mins)

We recommend you run an instance locally first.

[For Mac](https://nodered.org/docs/getting-started/local):
  ```
  sudo npm install -g --unsafe-perm node-red
  ```
  
[For Windows](https://nodered.org/docs/getting-started/windows):
  ```
  npm install -g --unsafe-perm node-red
  ```

Installing with AWS: <https://www.youtube.com/watch?v=ZcubOa9xESA>

## Step 2: Download or Clone repo (2 mins)
```
git clone https://github.com/abridged/dao-help.git

cd <cloned repo root folder path>

npm install
```

Start node red using command below
```
node-red  --userDir <cloned repo root folder path>
```

Once running, go to: http://localhost:1880

## Step 3: Configure and Cusomize
Node-Red Template Configuration Overview: https://www.youtube.com/watch?v=jNRvw86HGoM

**Update keyes in “Global Config” Configuration Nodes**

  * [Airtable API and App ID](https://airtable.com/invite/l?inviteId=invfw1mDN9Gm7qmO4&inviteToken=e2b07eee746127408d6dc64f6158dbdd78d3e195978d2a8d14779603222b5c42)- this is your database and user management system. [1 min tutorial](https://www.youtube.com/watch?v=tCC9z3-ahxs)
  * [Telegram Bot API](https://core.telegram.org/bots) - creating your own telegram bot is extremely easy, just find @BotFather and press start. [30 s tutorial](https://www.youtube.com/watch?v=WEJpuqTbQRU)
  * [DAO Configuration](https://mainnet.aragon.org/#/) - you need the DAO URL, voting app contract, vault/agent contract, finance app contract, DAO token contract, and the PK of the token premined address. [3 min tutorial](https://www.youtube.com/watch?v=bq8t62gyq2g)
  * [AWS IAM](https://aws.amazon.com/iam/) - create a key to administer the KMS system
  * [AWS KMS](https://aws.amazon.com/kms/) - this is how we store the private key for users' Ethereum accounts
  * [Wyre Account ID](https://dash.sendwyre.com/sign-in) - if you want to onboard using Wyre, make an account!
  
  
## Step 4: We recomend to restart node-red. 
To stop node-red press ctr+c

Start node-red again 
```
node-red  --userDir <cloned repo root folder path>
```

