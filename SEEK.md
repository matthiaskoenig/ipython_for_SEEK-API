# Local SEEK instance
Setup for local testing and development.

## Docker compose
```bash
cd ~/Download
sudo curl -L "https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

## Build seek
```
git clone https://github.com/seek4science/seek
cd seek

docker volume create --name=seek-filestore
docker volume create --name=seek-mysql-db
docker volume create --name=seek-solr-data
docker volume create --name=seek-cache

docker-compose up
```

## Instance
Seek is running on port `3000`
```bash
http://localhost:3000
```

## SEEK API
