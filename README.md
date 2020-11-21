# Safrie-blockchain #

## Naivechain-en oinarrituta ##

https://github.com/lhartikk/naivechain

## RUN SERVERS ##

```
bash server-01.sh
bash server-02.sh
```

params:
- COLLECTION: MONGODB collection name 
Example: COLLECTION=blockchain-01

- HTTP_PORT: Web server port
Example: HTTP_PORT=3001

- P2P_PORT: P2P port
Example: P2P_PORT=6001

## MONGODB ##

Create collection:

```
db.createCollection('blockchain-01');
db.createCollection('blockchain-02');
```

## HTTP API ##

### Get blockchain ###
```
curl http://localhost:3001/blocks
```
### Create block ###
```
curl -H "Content-type:application/json" --data '{"data" : "Some data to the first block"}' http://localhost:3001/mineBlock
``` 
### Add peer ###
```
curl -H "Content-type:application/json" --data '{"peer" : "ws://localhost:6001"}' http://localhost:3001/addPeer
```
### Query connected peers ###
```
curl http://localhost:3001/peers
```
