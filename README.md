# just4lex_microservices
just4lex microservices repository
### Logging-1

- Пересобраны образа
- Настроено логирование (Fluent, Elastic, Kibana)
- Устроили поиграйки с grokами
- Поднят трейсинг
- Было долго и немного больно, но вроде все получилось

### Docker-4
Можно, через -p:
docker-compose -p blabla up

### HW17
- Download src:
```
wget https://github.com/express42/reddit/archive/microservices.zip
unzip *.zip
cd src/
```
- Create dockerfile for microservices
- Build images
- Create network and run containers
- Make sure it works
- Make ui more lightweight
- Create volume for Mongo and mount em

### HW16
- Created docker host: 
```
yc compute instance create   --name docker-host   --zone ru-central1-a   --network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4   --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1804-lts,size=15   --ssh-key ~/.ssh/ubuntu.pub 
```

- Added context:

```
docker context create remote --docker "host=ssh://appuser@62.84.127.179"
docker context use remote
```

- Built image:
```
docker build -t reddit:latest .
```

- Started container:
```
docker run --name reddit -d --network=host reddit:latest
```
- Logged to hub
- Added image to hub
