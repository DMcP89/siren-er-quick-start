# Siren ER Quick Start

This repository can be used to quickly setup all the neccesary components to complete the [Getting Started with Siren ER](https://docs.siren.io/siren-er/2.0.0/siren-er/siren-er-getting-started.html) walkthrough.

## Prerequisites
* Docker
* Docker-Compose
* Git

## Make it go
1. Clone this repository
```
git clone https://github.com/DMcP89/siren-er-quick-start.git
cd siren-er-quick-start
```
2. Run docker compose
```
docker-compose up -d
```

## Running with a license
1. uncomment the following lines in the .env file
```
SENZING_ENGINE_CONFIGURATION_JSON='{
 "PIPELINE" : {
 "CONFIGPATH" : "/etc/opt/senzing",
 "RESOURCEPATH" : "/opt/senzing/g2/resources",
 "SUPPORTPATH" : "/opt/senzing/data",
 "LICENSEFILE" : "/opt/senzing/g2/g2.lic"
 },
 "SQL" : { "CONNECTION" : "postgresql://G2:password@host.docker.internal:5432:G2" }
}'
```

2. create the g2 directory under senzing_volume
```
mkdir senzing_volume/g2
```

3. copy your license file to the g2 directory
```
cp g2.lic senzing_volume/g2/g2.lic
```

4. Run docker compose
```
docker-compose up -d
```

