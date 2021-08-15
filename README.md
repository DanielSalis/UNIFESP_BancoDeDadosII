# UNIFESP_BancoDeDadosII
Instruções para uso (linux ,mac ou windows utilizando wsl2):

## 1) Subindo container
* Abra o primeiro terminal dentro do diretório
* execute: ```sudo docker-compose up```

## 2) Acessando container
* Abra o segundo terminal (sem fechar o primeiro)
* execute: ```sudo docker cp ./build.txt redis-db:/data```
    * comando responsável por copiar o arquivo build.txt para dentro do container
* execute: ```sudo docker-compose exec redis bash``` 
    * comando responsável por acessar o container do redis
* execute:  ```cat build.txt | redis-cli --pipe```
    * comando responsável por realizar os "creates" / "inserts" dentro do banco

* execute:  ```redis-cli```
    * comando para acessar a interface de comandos do redis

* dentro da interface é possivel executar os comandos desejados para as buscas
    * por exempo: ```HGETALL Cliente:"111.111.111-22"``` 
    * ou ```KEYS *``` para listar todas as chaves

## Comandos úteis
* FLUSHDB            --Apaga banco inteiro
* SADD myset "Hello" --Adiciona item ao set
* SMEMBERS myset:id  --Retorna os membros do set
* DEL myhash         --Deleta a hash 
