# dao-help

Collab19: NodeRed based bot system

Spin up your own Aragon DAO system inside of telegram using Abridged account contracts and an Aragon DAO framework! See Collab19 here as an example of what to anticipate: <https://t.me/collab19_bot>

## Pre-requisites

The Collab19 DAO template uses [Node-Red](https://nodered.org/), an open source visual development environment.

This project is built to run an [Aragon DAO](https://mainnet.aragon.org/) in telegram. You will need to spin one of those up to have the required links and contracts. We suggest using the Company Template to avoid unknown compatibility issues.

You will also need an [Airtable](https://airtable.com/) account to manage the DAO userbase, and you will need to create a bot in [Telegram](https://core.telegram.org/bots).

Last piece to note, the system uses Abridged account contracts to create an Ethereum account for new members. See the docs [here](https://abridged.gitbook.io/docs/) and find an interface for the SDK [here](https://preview.abridged.io/)

## Step 1: Download Node-Red (10 mins)

We recommend you run an instance locally first. Find options in the link below.

https://nodered.org/docs/getting-started/local

Otherwise, feel free to reference this video of installing with AWS: <https://www.youtube.com/watch?v=ZcubOa9xESA>

Here is the general "Getting Started" link: https://nodered.org/docs/getting-started/

## Step 2: Setup Collab19 Template (10 mins)
Download Dependencies, Configure Global Parameters and Upload the Collab19 Template.

Watch this short video for reference: https://www.youtube.com/watch?v=5vtwdUs7sPI

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
<B>
Update functtionGlobalContext section in settings.js as 
</B>

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

**Update keyes in “Global Config” Configuration Nodes

  * [Airtable API and App ID](https://airtable.com/invite/l?inviteId=invfw1mDN9Gm7qmO4&inviteToken=e2b07eee746127408d6dc64f6158dbdd78d3e195978d2a8d14779603222b5c42)- this is your database and user management system.
  * [Telegram Bot API](https://core.telegram.org/bots) - creating your own telegram bot is extremely easy, just find @BotFather and press start.
  * [AWS KMS](https://aws.amazon.com/kms/) - this is how we store the private key for users' Ethereum accounts
  * [AWS IAM](https://aws.amazon.com/iam/) - you also need this
  * [Wyre Account ID](https://dash.sendwyre.com/sign-in) - if you want to onboard using Wyre, make an account!
  * [Abridged Relayer](https://preview.abridged.io/) - a relayer endpiont from the Abridged SDK.


