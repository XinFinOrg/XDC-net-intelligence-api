XDC01 Network Intelligence API
============


This is the backend service which runs along with ethereum and tracks the network status, fetches information through JSON-RPC and connects through WebSockets to [eth-netstats](https://github.com/XinFinOrg/XDC-netstats) to feed information.


## Prerequisite
* eth, geth or pyethapp
* node
* npm
* pm2



## Configuration

Configure the app modifying [processes.json](/processes.json). Note that you have to modify the backup processes.json file located in `./bin/processes.json` (to allow you to set your env vars without being rewritten when updating).

```json
"env":
	{
		"NODE_ENV"        : "production", // tell the client we're in production environment
		"RPC_HOST"        : "localhost", // eth JSON-RPC host
		"RPC_PORT"        : "8545", // eth JSON-RPC port
		"LISTENING_PORT"  : "30303", // eth listening port (only used for display)
		"INSTANCE_NAME"   : "", // whatever you wish to name your node
		"CONTACT_DETAILS" : "", // add your contact details here if you wish (email/skype)
		"WS_SERVER"       : "ws://localhost:3000", // path to eth-netstats WebSockets api server
		"WS_SECRET"       : "Test_Secret", // WebSockets api server secret used for login
		"VERBOSITY"       : 2 // Set the verbosity (0 = silent, 1 = error, warn, 2 = error, warn, info, success, 3 = all logs)
	}
```

## Run

Run it using pm2:

```bash

pm2 start processes.json
```
## Contacting Us

Join our [Telegram Developer Group](https://t.me/XinFinDevelopers) and put up your queries or raise issue in Github to get answer. We would love to answer your questions.