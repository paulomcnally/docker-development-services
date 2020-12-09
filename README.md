Services for docker in my development environment.

- postgres:12.4
- redis:5.0.9
- mongo:4.4.1

```bash
$ git clone https://github.com/paulomcnally/docker-development-services.git
$ cd docker-development-services
$ docker-compose up -d
```

# Postgres

## Restore

Copy `latest.dump` file into `./dumps`.

```bash
docker exec postgres pg_restore --verbose --clean --no-acl --no-owner -U development -d my_database --schema=public /db/dumps/latest.dump
```

# MongoDB

## Restore

Copy `backup-dir-name` with bson files into `./dumps`.

```bash
docker exec mongo mongorestore --username development --password development /db/dumps/backup-dir-name
```