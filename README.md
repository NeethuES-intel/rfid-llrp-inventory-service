# RFID Inventory Service
## Overview
RFID Inventory Service - Edgex application service for processing tag reads,
producing events [ARRIVED, MOVED], configure and manage the LLRP readers via commands

## Installation and Execution ##

#### Prerequisites ####

 - Go language
 - GNU Make
 - Docker
 - Docker-compose

##### Build #####
```
$ make build
```
##### Execute unit tests with coverage #####
```
$ make test
```
##### Format #####
```
$ make fmt
```
##### Build Docker image #####
```
$ make docker
```

#### Commands Available
- Ping command to see if the service is up and running.
```
GET http://localhost:48086/ping

pong
```
- Command to get all the list of LLRP readers registered in edgex.
```
GET http://localhost:48086/command/readers

{"ReaderList":["192.168.1.78_5084"]}
```
- Command to make the LLRP reader start reading tags
```
POST http://localhost:48086/command/readings/StartReading

OK
```
- Command to make the LLRP reader stop reading tags
```
POST http://localhost:48086/command/readings/StopReading

OK
```

#### License
[Apache-2.0](LICENSE)
