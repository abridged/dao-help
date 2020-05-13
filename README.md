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

## Step 2: Setup NodeRed Environment (15 mins)

Watch this 7 min video for reference: https://www.youtube.com/watch?v=5vtwdUs7sPI

2.2 ``` ~/.node-red```
![](https://raw.githubusercontent.com/abridged/dao-help/master/images/Open%20Node%20Red.png)

2.3 Open the Package.json
![](https://raw.githubusercontent.com/abridged/dao-help/master/images/Edit%20Package.png)

2.4 Copy and Paste Dependencies 

Package.json dependencies to upload:

  ```
  "dependencies": {
      "@aws-crypto/client-node": "^1.0.4",
      "abridged": "^2.0.0-beta.2",
      "aws-sdk": "^2.659.0",
      "eth-sdk": "^0.2.8",
      "ethers": "^4.0.46",
      "node-fetch": "^2.6.0",
      "node-red-contrib-chatbot": "~0.18.15",
      "node-red-contrib-loop-processing": "^0.4.0",
      "node-red-contrib-simple-message-queue": "^0.2.5",
      "node-red-contrib-viseo-airtable": "github:alokt/node-red-contrib-airtable#master",
      "node-red-node-twitter": "~1.1.6",
      "telegraf": "^3.37.0",
      "ws": "^7.2.3"
  }
  ```

Before
![](https://raw.githubusercontent.com/abridged/dao-help/master/images/Package%20Before.png)
After
![](https://raw.githubusercontent.com/abridged/dao-help/master/images/Package%20After.png)

2.5 ```NPM Install```
![](https://raw.githubusercontent.com/abridged/dao-help/master/images/Install%20Dependencies.png)


2.6 Update functionGlobalContext section in settings.js



```
  functionGlobalContext: {
    abridged: require("abridged"),
    ethsdk: require("eth-sdk"),
    fetch: require("node-fetch"),
    ws: require("ws"),
    ethers: require("ethers"),
    telegraf: require("telegraf"),
    telegram: require("telegraf/telegram"),
    aws_client_node: require("@aws-crypto/client-node"),
    AWS : require('aws-sdk'),
  }
```

How to import flow into Node-Red

https://nodered.org/docs/user-guide/editor/workspace/import-export

## Step 3: Configure and Cusomize
Node-Red Template Configuration Overview: https://www.youtube.com/watch?v=jNRvw86HGoM

**Update keyes in “Global Config” Configuration Nodes**

  * [Airtable API and App ID](https://airtable.com/invite/l?inviteId=invfw1mDN9Gm7qmO4&inviteToken=e2b07eee746127408d6dc64f6158dbdd78d3e195978d2a8d14779603222b5c42)- this is your database and user management system.
  * [Telegram Bot API](https://core.telegram.org/bots) - creating your own telegram bot is extremely easy, just find @BotFather and press start.
  * [AWS KMS](https://aws.amazon.com/kms/) - this is how we store the private key for users' Ethereum accounts
  * [AWS IAM](https://aws.amazon.com/iam/) - you also need this
  * [Wyre Account ID](https://dash.sendwyre.com/sign-in) - if you want to onboard using Wyre, make an account!


