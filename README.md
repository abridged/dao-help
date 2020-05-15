# dao-help: estimated setup 1.5 hours.

## Intro to Collab19: NodeRed based DAO Ops bot system. 

**For an understanding of what you're creating, see [this bot](https://t.me/collab19_bot). Technical [support group](https://t.me/joinchat/Hgw0mRcKNRFH3FG5Zjr2SA).**

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

## Step 3: Configure and Cusomize (30 min - 1 hr)
See the Config tutorial videos below!

**API Key Explanations and Links**
Read more about the different API keys needed here.

  * [Airtable API and App ID](https://airtable.com/invite/l?inviteId=invfw1mDN9Gm7qmO4&inviteToken=e2b07eee746127408d6dc64f6158dbdd78d3e195978d2a8d14779603222b5c42)- this is your database and user management system. 
  * [Telegram Bot API](https://core.telegram.org/bots) - creating your own telegram bot is extremely easy, just find @BotFather and press start. 
  * [DAO Configuration](https://mainnet.aragon.org/#/) - you need the DAO URL, voting app contract, vault/agent contract, finance app contract, DAO token contract, and the PK of the token premined address.
  * [AWS IAM](https://aws.amazon.com/iam/) - create a key to administer the KMS system
  * [AWS KMS](https://aws.amazon.com/kms/) - this is how we store the private key for users' Ethereum accounts
  * [Wyre Account ID](https://dash.sendwyre.com/sign-in) - if you want to onboard using Wyre, make an account!

**API Key Config Tutorial Videos**
Watch the following videos to most quickly get you up to speed!

[Collab19 Template Overview](https://www.youtube.com/watch?v=1MjoDXFa2mU) (2.5 min)

[Airtable Config tutorial](https://www.youtube.com/watch?v=tCC9z3-ahxs) (1 min)

[Telegram Config tutorial](https://www.youtube.com/watch?v=WEJpuqTbQRU) (30 s)

[DAO Config tutorial](https://www.youtube.com/watch?v=bq8t62gyq2g) (3 min)

[AWS Config Tutorial](https://www.youtube.com/watch?v=jNxuRF5Yc3g) (3 min)

[Changing Copy in Node-Red](https://www.youtube.com/watch?v=FdgfPJDd0mE) (1 min)

Once complete, you will have a functioning DAObot, exactly the same as the Collab19 template. You are free to change and update new flows to this repo or to other repos as a way for more people to access different types of DAOs and DAO templates in Node-Red.
  
## Step 4: Stopping and Starting Node-Red
To stop node-red press ctr+c

To start node-red again 
```
node-red  --userDir <cloned repo root folder path>
```

