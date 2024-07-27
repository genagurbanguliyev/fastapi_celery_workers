# Asynchronous Tasks with FastAPI and Celery

Example of how to handle background processes with FastAPI, Celery, and Docker.

## Want to learn how to build this?

Check out the [post](https://testdriven.io/blog/fastapi-and-celery/).

## Want to use this project?

Spin up the containers:

```sh
$ docker-compose up -d --build
```

Try adding a few more workers to see how that affects things:
```sh
$ docker-compose up -d --build --scale worker=3
```

***
###### If you faced any errors during building try:
Rebuild Docker Images:
If the image has been updated or there are changes in the Dockerfile, you need to rebuild the images. Use the following command to ensure a clean build:

```sh
$ docker-compose down --volumes
$ docker-compose up --build
```

***

Open your browser to [http://localhost:8004](http://localhost:8004) to view the app or to [http://localhost:5556](http://localhost:5556) to view the Flower dashboard.

Trigger a new task:

```sh
$ curl http://localhost:8004/tasks -H "Content-Type: application/json" --data '{"type": 0}'
```

Check the status:

```sh
$ curl http://localhost:8004/tasks/<TASK_ID>
```