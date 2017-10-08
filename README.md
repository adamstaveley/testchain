## Mock blockchain 

This is a repository based on the tutorial provided by [Daniel van Flymen](https://hackernoon.com/learn-blockchains-by-building-one-117428612f46).

The Python version has been rewritten in Typescript with additional tests provided. The Python version will remain, potentially allowing for quick prototyping. 

### Running the Python version:
- Make sure your Python 3 version is 3.6 and you have pip3.
- Use pyvenv (virtual environment) for Python 3 if you wish to install dependencies locally rather than globally on your system.
- You can manage Python versions using Pyenv.
- Instructions below are for Ubuntu 17.04 - your system may be different. 
```
$ git clone https://github.com/adamstaveley/testchain.git
$ cd testchain/py-proto
$ pyvenv-3.6 venv venv (or equivalent) [optional]
$ source venv/bin/activate [optional]
$ pip install -r requirements.txt
$ python blockchain.py $PORT
```

### Building/Running the Typescript version
Requires Node (developed using >= 8.4) and NPM (>= 5.3). You can manage Node/NPM versions with NVM.
TypeScript is part of the dependencies and will be installed locally.
```
$ git clone https://github.com/adamstaveley/testchain.git
$ cd testchain/ts-main
```
- Install dependencies
```
$ npm install
```
- Run tests
```
$ sh bin/makeTest.sh
$ npm run build
$ npm test
```
- Run (will default to 8000 if no port specified)
```
$ npm start $PORT
```

### Endpoints
`GET /mine` - mine transaction\
`POST /transaction/new | application/json | {sender: string, recipient: string, amount: int}` - send transaction to be mined\
`GET /chain` - retrieve full chain\
`POST /nodes/register | application/json | {nodes: string[]}` - register new node address\
`GET /nodes/resolve` - resolve more recent chains 

### TODO:
- Extend tests
- Convert synchronous Blockchain class methods to asynchronous methods
- Provide automatic interaction between nodes