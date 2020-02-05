### Up and run databases for local development and tests using docker-compose

* install [docker](https://docs.docker.com/install/#supported-platforms) (18.06.0+)
* install [docker-compose]((https://docs.docker.com/compose/install/))
* clone this repo
* `cd dbdock`
* run required database:
  - `docker-compose up -d postgres-12`
  - `docker-compose up -d mssql-2017` (by default password is `saPass1234`)
  - `docker-compose up -d mysql-5`
* or run everything (not recommended):
  - `docker-compose up -d`

Launched services will be restarted on system reboot automatically, unless stopped manually (`restart: unless-stopped` policy is used). 

To stop database:

```
docker-compose stop mssql-2017
```

To see logs:

```
docker-compose logs -f mssql-2017
```

Data is stored in the corresponding subdirectories inside `db-data` directory 


### Adminer UI

A simple gui tool to work with databases: 

```
docker-compose up adminer
```

Access UI at http://localhost:81 . Use corresponding container name as server address e.g.: `mssql-2017`

