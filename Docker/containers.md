# Docker Containers

To make a new container, you need a `docker-compose.yml` file.

Here for example is my JellyFin docker compose file:
```yml
services:
  jellyfin:
    labels:
      glance.name: Jellyfin
      glance.icon: si:jellyfin
      glance.url: jellyfin.stemler.dev
      glance.description: Media library. Movies, music, books, and shows
    image: jellyfin/jellyfin:latest
    container_name: jellyfin
    ports:
      - "8096:8096"
    volumes:
      - ./config:/config
      - ./cache:/cache
      - /home/tho/media:/media
    restart: unless-stopped
```

At the top is the `services` tag. This lets docker know all the services we will be deploying.
Inside of `services` we list our services, like this `service-name:` 
where service name is the name of our service. In this example my service is named jellyfin. 
You can have multiple services in one `services` tag! Look at my Immich compose file.

Inside each service needs to atleast have a `image` tag and a `container-name` tag.

### `image` tag

The image tag has the reference to the image we want to deploy. In this instance it is jellyfin/jellyfin:lastest
Refer to each containers documentation for what image to reference.

### `container-name` tag

This one is simple. This is the name associated with the container, for use in logging and access.

Along with those two tags you can also add `volumes`, `ports`, and `labels`!

### `volumes` tag

This tag is where you list all the directories you want the container to have access too.
For instance, in my JellyFin container I give it three volumes `/config`, `/cache`, and `/media`.
These volumes are written like this: `- <path-to-dir>:<"path"-to-volume>`
where the first path is the actual path to the dir, and the second path
