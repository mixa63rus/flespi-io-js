### class Connection
Connection make global connector by passed config
The arguments are:
* `config` is a global config for all connections you have
    * `connectorName` is a name of global variable of connector(only for initialization Vue plugin)
    * `token` is a token for connections
    * `httpConfig` config for http connections
        * `server` server for http connections
        * `port (optional)` port for http connections
    * `socketConfig` config for mqtt connections by socket
        * `server` server for mqtt connections
        * `port (optional)` port for mqtt connections
        * `clientId (optional)` client id for mqtt connections
        * `mqttSettings` mqtt settings by MQTT.js API
 
        
### getters and setters

```js
let connector = new Connection({
  token: 'FlespiToken xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',
  httpConfig: { server: 'https://server.io', port: 8080 },
  socketConfig: { server: `ws://server.io`, mqttSettings: {
            reschedulePings: true,
            keepalive: 3600,
            resubscribe: false,
            reconnectPeriod: 5000,
            connectTimeout: 3600000
        }
    }
})
```

* Token

```js
let token = connector.token
connector.token = 'FlespiToken XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX'
```

* httpConfig

```js
let httpConfig = connector.httpConfig
connector.httpConfig = { server: 'http://server.io', port: 80 }
```

* mqttConfig

```js
let socketConfig = connector.socketConfig
connector.socketConfig = { server: 'ws://mqtt.server.io', mqttSettings: {
                reschedulePings: true,
                keepalive: 3600,
                resubscribe: false,
                reconnectPeriod: 5000,
                connectTimeout: 3600000
            }
        }
```