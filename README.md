- Run Docker Compose: `docker compose up -d` / `docker compose up`

- Check Docker Compose's volumens status: `docker compose ps -a` / `docker compose ps`

- Remove Docker's images: `docker rmi -f imageID1 imageID2 ...` (-f = force)

- Copy a file to the docker we want to: `docker cp file docker_id:/dir`

- Check Docker's images: `docker images -a`

- Remove all dangling (not tagged or associated with a container) containers, volumes, networks and images: `docker system prune`, for unused `docker system prune -a`

- Shows all unused local images: `docker images ls -f dangling=true`

- Shows all unused local volumes: `docker volume ls -f dangling=true`

- Remove all local volumes not used by at least one container: `docker volume prune`
  
- Enter to a Docker's volumen: `docker compose exec VolumenID sh` / `docker compose exec VolumenID bash`
