# ibm-mq-quickstart
Quick setup for IBM MQ Series Server and an Efficient MQ Tester

Pre-requisites:
- Install Docker (Tested on MacOSX and Linux variants)
- Install Java JRE (The client tool will prompt you)
## Install Server

- `cd mqserver`
- `docker build -t my-ibmmq .`
- `docker images` (should show sucessfully built image with repository name my-ibmmq)
- `docker run -it -p 1414:1414 -p 9443:9443 my-ibmmq`
- `docker container ls -a` (should show STATUS and PORTS)
- (optional) `docker inspect <CONTAINER ID>` (show external IP address - sometimes useful if localhost acts weird)
- https://localhost:9443 will get you to the admin console: username: admin; password: password1

## Install Client
- client executibles are located in `mq-test-james` folder
- `./run.sh` -- help to ensure client is working
- `vim test1.properties` file - you shouldn't have to change anything for a locally running queue. Otherwise, change `HOST_NAME` as necessary.

## Single Message Test
- `./put.sh test1.properties data.txt` -- this will put the data on `HOST_QUEUE=DEV.QUEUE.1`. <img width="300" align="right" alt="center" src="https://user-images.githubusercontent.com/30869911/90060721-24a0dc00-dcb3-11ea-95a1-5dde5df87c8e.png">
- `./get.sh test1.properties` -- this will remove the data on `HOST_QUEUE=DEV.QUEUE.1`.

## Multiple Message Test
- `./put.sh test1.properties 20 data.txt` -- this will put the 20 messages on `HOST_QUEUE=DEV.QUEUE.1`. <img width="300" align="center" alt="multiple" src="https://user-images.githubusercontent.com/30869911/90062034-089e3a00-dcb5-11ea-8db8-69deaf3282c1.png">

- `./get.sh test1.properties` -- this will remove the data on `HOST_QUEUE=DEV.QUEUE.1`.





