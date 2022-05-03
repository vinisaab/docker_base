# DOCKER
    docs.docker.com
### Camadas
    - A imagem do container é dividida em camadas
        - Somente a Ultima camada pode ser escrita, as outras são de leitura

### Espaço
    - Uma imagem tem 5GB
    - Preciso subir 10 instancias, qual espaço ele irá usar, 50GB?
        - Não, apenas 5GB, o docker usa a mesma imagem para subir as instâncias, gerando e espaço apenas os dados que irão ser criados. (Logs, etc.)

### Kernel
    - O DOCKER utiliza o kernel do host onde ele está instalado.
    - Netfilter(IPtables)
        - Redirect
    - Namespaces
        - PID - Isolamento de proceços
        - NET - isolamento de Redes 
        - MNT - Mount Points
        - USER - Usuários
    - CGroups
        - Isolamento de CPU e Memória e  Disco

## Instalando o DOCKER
    https://docs.docker.com/install

    - curl -fsSL https://get.docker.com | bash
    - docker -v (Versão)
    - docker container ls 
        - Mostra os containers em execução
    - docker container ls -a

## Comandos
    - docker container run hello-word:latest
        - Executar a imagem hello-word
        - Ultima Versão    
    - docker container run -ti ubuntu
        - Executa a imagem ubuntu com um terminal interativo
    - docker container ls 
        - Mostra os containers em execução
    - docker container ls -a
        - Mostrra imagens baixadas
    - CTRL + p + q
        - Sai do container sem parar o serviço
    - docker container attach [container id]
        - Entra novamente em um container ainda em execução
    - docker run -d nginx
        - Excuta a imagem como daemon(background)
    - docker container exec -ti [container id] bash
        - executa um comando dentro do container, neste caso bash

## MSG
    - Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
        - sudo service docker start
    - docker: Got permission denied while trying to connect to the Docker daemon socket at unix:
        - sudo chmod 666 /var/run/docker.sock
