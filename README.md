# Goals
Create a docker container and expose the debug port and remotely attach a debugger to debug unit tests.

Why am I doing this? In some of the architectures I work on python needs to be fully containerized due to conflicts with the underlying system architecture.

# Setup
```
# Initialized a python project and added it to version control
cookiecutter https://github.com/karec/cookiecutter-flask-restful
```

* Build the docker image

