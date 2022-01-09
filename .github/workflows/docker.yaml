name: Nginx website workflow

on:
  push:
    branches:
      - "master"

jobs:
  docker:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: setup Docker Buildx
        uses: docker/setup-buildx-action@v1
      - name: login to DockerHub
        uses: docker/login-action@v1
        with:
          username: ${{secrest.DOCKERHUB_USERNAME}}
          password: ${{secrest.DOCKERHUB_TOKEN}}
      - name: Build and push
        uses: docker/build-push-action@v1
        with:
          context: .
          push: true
          tags: ${{secrest.IMAGE_TAG}}:latest
