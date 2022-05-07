# ChainKVS

## About this project
- Chain-replicated KVS
- Can handle up to 256 simultaneous clients with up to 1024 concurrent requests each
- Up to 16 chain-replicated servers
- PUTs are sent to the head server, GETs are retrieved from the tail server
- Failure detection using FCheck, data is synchronized to servers once the chain has reorganized itself


