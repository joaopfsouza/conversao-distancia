# Conversao Distância


## Docker

### Docker Build/Run

```shell
# Variavles
export DOCKER_IMAGE_NAME="conversor-distancia"
export DOCKER_TAG="latest"

# docker build
docker build -t $DOCKER_IMAGE_NAME:$DOCKER_TAG .

docker run --rm --detach --name conversor-distancia -p 5000:5000 $DOCKER_IMAGE_NAME:$DOCKER_TAG
```

### Docker Hub

```shell
# Variavles
export DOCKER_PASSWORD="password"
export DOCKER_USER="username" 
export DOCKER_IMAGE_NAME="conversor-distancia"
export DOCKER_TAG="latest"

# docker login
echo $DOCKER_PASSWORD | docker login -u $DOCKER_USER --password-stdin

# docker build
docker build -t $DOCKER_IMAGE_NAME:$DOCKER_TAG .

# docker tag
docker tag $DOCKER_IMAGE_NAME:$DOCKER_TAG $DOCKER_USER/$DOCKER_IMAGE_NAME:$DOCKER_TAG

# docker push
docker push $DOCKER_USER/$DOCKER_IMAGE_NAME:$DOCKER_TAG
```