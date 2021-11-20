# send
An implementation of https://github.com/timvisee/send

## Deploy
- Get a server running docker with docker compose or docker swarm with ports 80 and 443 free
- In `docker-compose.yml`, Replace `localhost` (in both the send and caddy services) with your fully qualified hostname  `myserver.example.com`
- Run `docker compose up`, or `docker-compose up`, or `docker stack deploy -c docker-compose.yml send`

If your system is available from the internet, caddy will keep your certificate valid and up to date with let's encrypt.

## More Configuration

Default variables set for send are:
- FILE_DIR: /uploads (this shouldn't be changed, you'll get a permissions error)
- EXPIRE_TIMES_SECONDS: 3600,86400,604800,2592000 (1 hour, 1 day, 7 days, 30 days)
- DEFAULT_EXPIRE_SECONDS: 604800 (1 day)
- MAX_EXPIRE_SECONDS: 2592000 (30 days)
- MAX_FILE_SIZE: 10737418240 (10GB)
- DEFAULT_DOWNLOADS: 5

Send is very configurable. You can use S3 or GCP for backend storage instead of `/uploads`. More information:
https://github.com/timvisee/send/blob/master/docs/docker.md
