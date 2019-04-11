# SEEK API
Example ipython notebook to use the SEEK writeAPI (SEEK version 1.8.1+, https://github.com/seek4science/seek).
 
Creates a `Project --> Investigation --> Study --> Assay(s) --> Assets`, all based on each other, which result in the following ISA structure:
![alt text](https://raw.githubusercontent.com/hleonov/ipython_for_SEEK-API/master/ISA_Structure.png)

The Event and the Publication are not included in the code (Event is possible to add, Publication is not yet in the writeAPI code). 

In addition, contains examples on how to POST assets both based on uploads, or remote URLs, and an Assay with links to pre-existing assets.

'token' should contain a base64 encrypted "username:password" string to your SEEK instance.


## Installation
Setup python virtual environment
```
mkvirtualenv seek --python==python3.6
(seek) pip install -r requirements.txt --upgrade
(seek) pip install jupyterlab --upgrade
(seek) python -m ipykernel install --user --name seek --display-name "seek"
(seek) jupyter lab
```

## API token
For the connection with the database an API token is required.
Make sure this token is not tracked in the repository.

```
echo -n 'user:password' | base64 > token
```

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
Swagger documentation is avaiblable here:  
https://app.swaggerhub.com/apis/FAIRDOM/SEEK/0.1