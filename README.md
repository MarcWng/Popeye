systemctl start docker

docker-compose up -d --build

docker-compose restart

docker-compose up -d --build --remove-orphans