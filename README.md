# ChainKVS

## About this project
- Chain-replicated KVS
- Can handle up to 256 simultaneous clients with up to 1024 concurrent requests each
- Up to 16 chain-replicated servers
- PUTs are sent to the head server, GETs are retrieved from the tail server
- Failure detection using FCheck, data is synchronized to servers once the chain has reorganized itself

## More info & Spec
- see [here](https://github.com/jmhirsch/ChainKVS/blob/main/ChainedKVS%20Spec.pdf) for the full spec
- Developed for CPSC 416

## Running

1. Clone the repo & navigate to the project folder

2. Start the tracing server (must be done first)

   ```bash
     go run cmd/tracing-server/main.go
   ```

3. Start the Coord (must be done second)

   ```bash
     go run cmd/coord/main.go
   ```

4. Start the servers. Additional or fewer servers can be started by changing the config files. The servers do not have to be local, they can be on any machine, provided that the config files are modified with the correct IPs for each server.
 
   By default, 5 servers are configured.

   ```bash
     go run cmd/server/main.go
     go run cmd/server/main2.go
     go run cmd/server/main3.go
     go run cmd/server/main4.go
     go run cmd/server/main5.go
   ```

5. Finally, start the client. Multiple client instances can be started provided multiple config files are created. The source code of the client can be altered to change the number and type of requests

   ```bash
     go run cmd/client/main.go
   ```

## Credits
- Sassan Shokoohi
- Naithain Bossee
- Jonathan Hirsch
