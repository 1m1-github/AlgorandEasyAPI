# AlgorandEasyAPI
a web3 API service for Algorand accessible from web2

AlgorandEasyAPI would be `js` or `wasm` code (4) saved on the `IPFS` network that essentially contains

* an algorand sdk
* a wallet connect (WC) sdk

and exposes a simple API to frontend devs to

* connect a user to an Algorand account (1)
* send transactions of arbitrary complexity to Algorand (2)
* query the chain (3)

AlgorandEasyAPI saves frontend devs from learning and importing an algorand sdk and a WC sdk and a QR code sdk  

Importantly, AlgorandEasyAPI is essentially a 'server' on IPFS ~ it returns code that can be run locally  
This allows devs to offload complex code into services

## frontend dev process

1. HTTP GET AlgorandEasyAPI `js` or `wasm` (4) code from `IPFS`
2. run `js` or `wasm` code (e.g. in a webviewer) and ask it for a new WC session -> WC url and svg of qr code
3. either launch url or display the QR code. launch is good if they already have a WC wallet installed  
4. run `js` or `wasm` code and ask it for the account address of the connected session (given the WC url) -> account [is this possible?]
5. run `js` or `wasm` code and ask it to run a specific transaction

this transaction can be encoded in a simple manner (e.g. list of `goal` cli keywords)
now the frontend dev can craft arbitrarily complex transactions and let the `js` or `wasm` send them to Algorand

all the users of the frontend are fully safe using their Pera wallet (or another WC wallet)

## details

(1)
create new WC session
method that returns a new WC session url
the user will connect on their Pera app after following the url

(2)
// todo
find friendly encoding for arbitrary Algorand transaction groups
`js` API will decode and execute given a session id

(3)
similar to (2)

(4)
we should return code that can be run in as many frontends as possible  
`js` can be a good candidate bc maybe frontend frameworks can presumably run a webview
`wasm` would be another good candidate
is there another bytecode level or so encoding that can be run on more frontends
