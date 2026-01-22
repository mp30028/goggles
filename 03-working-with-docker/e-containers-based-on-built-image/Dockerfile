FROM ubuntu:latest

RUN apt update -y && apt upgrade -y && apt install -y nano openssh-client openssh-server        
CMD ["service", "ssh", "start"]
