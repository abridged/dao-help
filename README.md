# dao-help

Collab19: NodeRed based bot system

Spin up your own Aragon DAO system inside of telegram using Abridged account contracts and an Aragon DAO framework! See Collab19 here as an example of what to anticipate: https://t.me/collab19_bot

## Step 1: Download Node-Red (10 mins)

Video of installing with AWS: https://www.youtube.com/watch?v=ZcubOa9xESA

https://nodered.org/docs/getting-started/

https://nodered.org/docs/getting-started/local

https://nodered.org/

## Step 2: Setup Collab19 Template (10 mins)
Download Dependencies, Configure Global Parameters and Upload the Collab19 Template.

Watch this short video for reference: https://www.youtube.com/watch?v=5vtwdUs7sPI

Package.json dependencies to upload:

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

<B>
Update Node-Red settings.js
</B>
  Update below env into settings.js. This is just before module.exports

    process.env.AWS_ACCESS_KEY_ID = "<your aws access key>";
    process.env.AWS_SECREAT_ACCESS_KEY = "<your aws secret access key>";
    process.env.KMS_GENERATOR_KEY_ID = "<your kms generator key>";
    process.env.KMS_KEY_ID = "your kms generator key id";

<B>
Update functtionGlobalContext section in settings.js as 
</B>
  
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
        env: process.env
     }

Sample settings.js example (To-Do: Insert link here)

How to import flow into Node-Red

https://nodered.org/docs/user-guide/editor/workspace/import-export

## Step 3 Configure and Cusomize

Update keyes in “Global Config” Configuration Nodes

Node-Red Template Configuration Overview: https://www.youtube.com/watch?v=jNRvw86HGoM

Please find config screenshots here: https://github.com/abridged/dao-help/tree/master/images

Airtable Database

Collab19 uses airtable as a database to manage user access and associate their telegram IDs with their account contracts.
Copy this [table](https://airtable.com/invite/l?inviteId=invfw1mDN9Gm7qmO4&inviteToken=e2b07eee746127408d6dc64f6158dbdd78d3e195978d2a8d14779603222b5c42) to manage the database.

Telegram Bot

Creating your own telegram bot is extremely easy, just find @BotFather and press start.
https://core.telegram.org/bots
