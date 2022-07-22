# AlgorandEasyAPI
a web3 API for Algorand accessible from web2

**note: perhaps the goal of this project is actually better achieved via the AlgoExplorer REST API plus a friend transaction group encoding compiler (into bytecode) ~ but n algorand-sdk with AlgoExplorer REST API actually basically does the same**

AlgorandEasyAPI would be `js` code saved on the `IPFS` network that essentially contains

* an algorand sdk
* a wallet connect (wc) sdk

and exposes a simple API to frontend devs to

* connect a user to an Algorand account (1)
* send transactions of arbitrary complexity to Algorand (2)
* query the chain (3)

AlgorandEasyAPI saves frontend devs from learning and importing an algorand sdk and a wc sdk

## frontend dev process

1. HTTP GET AlgorandEasyAPI js code from IPFS
2. run js code (e.g. in a webviewer) and ask it for a new wc session -> wc url
3. either launch url or display as QR code. launch is good if they already have a wc wallet installed.
4. run js code and ask it for the account address of the connected session (given the wc url) -> account [is this possible?]
5. run js code and ask it run a specific transaction

this transaction can be encoded in a simple manner (e.g. list of `goal` cli keywords)
now the frontend dev can craft arbitrarily complex transactions and let the js send them to Algorand

all the users of the frontend are fully safe using their Pera wallet (or another wc wallet)

## details

(1)
create new wc session
method that returns a new wc session url
the user will connect on their Pera app after following the url

(2)
// todo
find friendly encoding for arbitrary Algorand transaction groups
js API will decode and execute given a session id

(3)
similar to (2)
