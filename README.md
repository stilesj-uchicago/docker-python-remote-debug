# Goals
Create a docker container and expose the debug port and remotely attach a debugger to debug unit tests.

Why am I doing this? In some of the architectures I work on python needs to be fully containerized due to conflicts with the underlying system architecture.

# Setup
```
# Initialized a python project and added it to version control
cookiecutter https://github.com/karec/cookiecutter-flask-restful
```

* Build the docker image
```
docker build --tag "jaystile/docker-python-remote-debug:latest" -f ./Dockerfile .
```

* Bring up the docker container
```
docker-compose -f ./docker-compose.yml up
```

* `exec` into the container to start the debug command
```
docker exec -it docker-python-remote-debug-web-1 bash
```

* star the debugger in the container
```
python -m debugpy --listen 0.0.0.0:5678 --wait-for-client -m pytest -lvx tests/test_user.py
```
