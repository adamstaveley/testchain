## Mock blockchain 

This is a repository based on the tutorial provided by [Daniel van Flymen](https://hackernoon.com/learn-blockchains-by-building-one-117428612f46).

The Python version has been rewritten in Typescript with additional tests provided. The Python version will remain, potentially allowing for quick prototyping. 

### Running the Python version:
- Make sure you have Python 3.6, pip3.
- Use pyvenv (Python virtual environment) if you wish to install dependencies locally rather than globally on your system.
- You can manage Python versions using e.g. Pyenv.
- Instructions below are for Ubuntu 17.04 - your system may be different. 
```
$ git clone https://github.com/adamstaveley/testchain.git
$ cd testchain/py-proto
$ pyvenv-3.6 venv venv (or equivalent) [optional]
$ source venv/bin/activate [optional]
$ pip install -r requirements.txt
$ python blockchain.py $PORT
```

### Running the Typescript version
```
$ git clone https://github.com/adamstaveley/testchain.git
$ cd testchain/ts-main
$ npm install
$ npm run build
$ npm start $PORT
```

### Endpoints
`GET /mine` - mine transaction\
`POST /transaction/new | application/json | {sender: string, recipient: string, amount: int}` - send transaction to be mined\
`GET /chain` - retrieve full chain\
`POST /nodes/register | application/json | {nodes: string[]}` - register new node address\
`GET /nodes/resolve` - resolve more recent chains 


TODO:
- convert synchronous code to asynchronous
- write tests


Resources:
- `echo 'hello world' | sha256sum | sed -e 's/\s\+-//'`
- Google: blockchain consensus types


