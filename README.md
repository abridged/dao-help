# dao-help

Collab19: NodeRed based bot system

Requirements includes:

Node-Red <https://nodered.org/>
<https://nodered.org/docs/getting-started/>

Airtable
<https://airtable.com/> (To-Do: Create Collab19 airtable templet and share link here)

Telegram Bot
<https://core.telegram.org/bots>

AWS account

Once NodeRed is installed update package.json dependencies as

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
  }

Sample settings.js example (To-Do: Insert link here)

<B>
How to import flow into Node-Red
<B>
  
<https://nodered.org/docs/user-guide/editor/workspace/import-export>

<B>
Update keyes into “Global Config” configuration nodes
</B>
