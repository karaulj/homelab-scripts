# homelab-scripts
Useful "scripts" for managing a Linux server running Docker apps.

All scripts in this repo must be included in PATH. For example:
```
cd homelab-scripts/
sudo mkdir /scripts
mv * /scripts
export PATH="$PATH:/scripts"
```

## docker-down
Stops all Docker containers in `/docker/docker-compose.yaml`.

## docker-ls
List all running Docker containers (not just in `/docker/docker-compose.yaml`). All additional args are passed to the underlying `docker container ls` command.

```
docker-ls -aq    # list all Docker containers (not just those that are running) and only print their container ID's.
```

## docker-up
Starts all Docker containers in `/docker/docker-compose.yaml`.

## free-space
List the amount of free space in attached storage (defaults to `/dev/sda1`).

## git-untracked
List all untracked files in a local git repo.

## ha-down
Stops all running Home Assistant Supervised containers.

## ha-ls
Lists all Home Assistant Supervised containers.

Installing Home Assistant *Supervised* through the [official installer](https://github.com/home-assistant/supervised-installer), means you can't start/stop the application via docker-compose. `ha-up` and `ha-down` provide similar functionality. `ha-ls` returns all HA Supervised containers (including addons) and is used by `ha-up` and `ha-down`.

All additional args are passed to the underlying `docker container ls` command. For example:

```
ha-ls -aq    # list all HA containers (not just those that are running) and only print their container ID's.
```

## ha-up
Starts all Home Assistant Supervised containers. 

## mount-nas
Mounts an NFS from a Synology NAS under the `/nas` directory.

## server-down
Stops all applications on this server. Runs `ha-down` and `docker-compose down` with a specified .yaml file (default: `/docker/docker-compose.yaml`).

## server-ls
Lists all applications on this server. Just calls `docker-ls` under the hood.

## server-up
Start all applications on this server. Runs `ha-up` and `docker-compose up -d` with a specified .yaml file (default: `/docker/docker-compose.yaml`).
