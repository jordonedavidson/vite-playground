# Vite Playground

**A convinient place to start a new Vite based JS/TS project.**

## How to start

Clone this project then:

1. Remove the .git folder to decouple your code from the starter.
2. Update the CONTAINER_NAME and APP_PORT values in the `.env` file to your liking.
3. Set the name and description in `package.json` for your project.
4. Run `git init` to set up version control.

## First run

In the `docker-compose.yml` file make sure the line `command: npm install` is uncommented, and run `docker-compose up` from the command line.

After the container is finished you will have a `node_modules` directory and a new `package-lock.json` file.

## Subsequent runs.

In `docker-compose.yml` comment out `command: npm install` and uncomment `command: "npm run dev -- --host"`.

Run `docker-compose up -d` from the command line.

Now you will have a running docker container with the name you gave it in `.env` and a website running on your localhost at the port specified in `.env`.

## Development

Saved changes to your code are picked up immediately by vite and displayed on the website in realtime.

### Adding packages.

To add packages to your project you need to connect to the command line of the docker container. For a container named `my-project` run `docker exec -it my-project sh`

From the command line you can run any npm commands you like.

### Restarting parcel

Should any updates to packages or configurations require you to restart parcel you can simply restart the docker container by running:

- `docker-compose down` then
- `docker-compose up -d`
