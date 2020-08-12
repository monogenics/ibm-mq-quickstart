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



