## API for Tron Web3 Domains

dApp Mainnet: https://trxdomains.xyz/app

Use NPMJS: https://github.com/TronWeb3Domains/trondomainjs/blob/main/README.md

Contract Address (Mainnet): TAtgoVq9xqv1C65hjFTerJQZFt4rbAPea6 - https://tronscan.io/#/contract/TAtgoVq9xqv1C65hjFTerJQZFt4rbAPea6/code

### Get Balance of Domains

Endpoint: https://app.trxdomains.xyz/api/domains/getBalance?address=TSFquXZoXtei19kDJ1Sy1YGjznz8gWhfKd&network=mainnet

**Method: GET**

**Param:**

address: 'TSFquXZoXtei19kDJ1Sy1YGjznz8gWhfKd'

network: 'testnet' // mainnet default

metadata: true // false default return metadata along with domain information

**Return:** 
```
{
    "status": true,
    "message": "Success",
    "data": 10
}
```

Endpoint: https://app.trxdomains.xyz/api/domains/getOwner?domain=trxmini.trx&network=mainnet

**Method: GET**

**Param:**

domain: 'trxmini.trx'

network: 'testnet' // mainnet default

metadata: true // false default return metadata along with domain information

**Return:** 
```
{
    "status": true,
    "message": "Success",
    "data": { 
        "owner": "...",
        "hex": "...",
        "metadata": [
        ]
    }
}
```
### Get a domain default from address
Get a domain default from a user's address, requiring the user to set the default domain name initially.
This will designate one of your domain to represent your account and act as your cross-platform Web3 username and profile. You can only have one Primary Domain per wallet address and can change it at any time. Steps to "Set Primary" domains:
1. Goto dApp: trxdomains.xyz/app
2. Connect wallet, show the list of created domains, click the "Set Primary" button below each domain (you need a gas fee to complete the transaction), reload the dapp to see the results shown above.

Endpoint: https://app.trxdomains.xyz/api/domains/getDomain?address=TSFquXZoXtei19kDJ1Sy1YGjznz8gWhfKd&network=mainnet

**Method: GET**

**Param**

address: TSFquXZoXtei19kDJ1Sy1YGjznz8gWhfKd ... // wallet address

network: 'testnet' // mainnet default

**Return:** 
```
{
    status: true,
    message: "Success",
    data: "trxdomain.trx"
}
```

### Get all domains owned by address
This GET method gets all the domains owned by an wallet address.

Endpoint: https://app.trxdomains.xyz/api/domains/getDomains?address=TSFquXZoXtei19kDJ1Sy1YGjznz8gWhfKd&network=mainnet

**Method: GET**

**Param**

address: TSFquXZoXtei19kDJ1Sy1YGjznz8gWhfKd ...

network: 'testnet' // mainnet default

**Return:** 
```
{
    status: true,
    message: "Success",
    data: ["trxdomain.trx","multiverse.trx" ..]
}
```


### Get Metatada
Get a value of metadata from the domain name

Endpoint: https://app.trxdomains.xyz/api/domains/getMetadata?key=website,twitter&domain=trxdomain.trx&network=mainnet

**Method: GET**

**Param**

keys: 'website,social:twitter'

domain: 'trxdomain.trx'

network: 'testnet' // mainnet default

**Return:** 
```
{
    status: true,
    message: "Success",
    data:
        { 
            "metadata": [
                {"key": "social:twitter","value":"https://twitter.com/trxdomains"},
                {"key": "website","value":"https://trxdomains.xyz"}
            ]
        }
}
```


