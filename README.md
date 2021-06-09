# homelab-scripts
Useful "scripts" for managing a Linux server running Docker apps.

All scripts in this repo must be in the same directory and included in your PATH.

## ha-ls
If you decided to install Home Assistant *Supervised* through the [official installer](https://github.com/home-assistant/supervised-installer), and therefore can't start/stop the application via docker-compose, `ha-up` and `ha-down` provide the same functionality. `ha-ls` returns all HA Supervised containers (including addons) and is used as input for for `ha-up` and `ha-down`.

## ha-up
Starts all Home Assistant Supervised containers.

## ha-down
Stops all running Home Assistant Supervised containers.

## server-up
Start all applications on this server. Runs `ha-up` and `docker-compose up -d` with a specified .yaml file (default: `/docker/docker-compose.yaml`).

## server-down
Stops all applications on this server. Runs `ha-down` and `docker-compose down` with a specified .yaml file (default: `/docker/docker-compose.yaml`).
