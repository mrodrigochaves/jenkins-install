### Instalação do Jenkins com Docker em Ubuntu 20.04

Projeto de provisionamento de servidor de automação Jenkins com o Docker.

# 💻 Stacks utilizadas:
![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white) ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white) 


## Instalando Docker

    apt install apt-transport-https ca-certificates curl software-properties-common

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

    apt-cache policy docker-ce

    apt install docker-ce

    docker version

## Instalando o jenkins:
    
    docker run \
    --name jenkins-docker \
    -u root \
    --rm \
    -d \
    --network jenkins \
    --network-alias docker \
    -p 8030:8080 \
    -p 50000:50000 \
    -v jenkins-data:/var/jenkins_home \
    -v /var/run/docker.sock:/var/run/docker.sock \
    --publish 2376:2376 \
    jenkinsci/blueocean

## Acessando Jenkins
Acesse a URL: localhost:8030 ou URL: seuip:8030

- Insira a sua senha de acesso
- Configure seu Jenkins e pronto!

### Referências

* [Jenkins](https://www.jenkins.io/doc/book/installing/docker/)
* [Docker](https://hub.docker.com/r/jenkins/jenkins)