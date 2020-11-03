# linux-docker-installation-manual

## Procedimento de instalação:

1. Remova possíveis versões antigas do Docker:
```
sudo apt-get remove docker docker-engine docker.io
```
2. Atualize o banco de dados de pacotes:
sudo apt-get update

3. Adicione ao sistema a chave GPG oficial do repositório do Docker:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

4. Adicione o repositório do Docker às fontes do APT:
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

5. Atualize o banco de dados de pacotes:
```
sudo apt-get update
```
6. Instale o pacote docker-ce:
```
sudo apt-get install docker-ce
```
7. Verifique a versão do Docker instalada
```
sudo docker version
```
8. Para executar o Docker sem precisar de sudo, adicione o seu usuário ao grupo docker:
```
sudo usermod -aG docker $(whoami)
```
## Docker Hello World!

Execute o comando:
```
docker run hello-world
```

O Docker vai buscar pela imagem hello-world localmente, e caso ela não existe
vai fazer o download da mesma no Docker Store. Com a imagem em mãos, o Docker vai criar um container
apartir desta imagem e executá-lo:

```
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
0e03bdcc26d7: Pull complete 
Digest: sha256:8c5aeeb6a5f3ba4883347d3747a7249f491766ca1caa47e5da5dfcf6b9b717c0
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

```
