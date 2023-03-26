# dockerized-springboot-app

Create image from Dockerfile:
docker build -t [image_name] .

Run container from created image:
docker run --name [container_name] -p external:internal [image_name]

Run docker compose:
docker-compose up
