# Tutorial on Microservices with Docker, Flask, and React

[![Build Status](https://travis-ci.com/Bi0max/testdriven-tutorial.svg?branch=master)](https://travis-ci.com/Bi0max/testdriven-tutorial)

# ToDo:
1. Fix TravisCI pipeline, which isn't working as expected because:
    1. Docker-compose exec always return exit code 0, not an error code of the command
    2. Sometimes tests start before PostgreSQL server is started

# Docker Toolbox for Windows configuration
1. [Confiure VirtualBox to have access to the volume folder](https://medium.com/@Charles_Stover/fixing-volumes-in-docker-toolbox-4ad5ace0e572)
    1. Set env variable `TESTDRIVEN_ROOT_FOLDER` (only for Windows), it will be used in docker-compose-dev.yml.
    For more info, check [this](https://docs.docker.com/compose/compose-file/#variable-substitution).
    2. Refer to it from docker-compose "volumes" or from docker run "-v" option
    3. Refer just by the name you gave it in the settings (Shared Folders) of VirtualBox
2. [SSH into docker machine as root](https://stackoverflow.com/questions/32646952/docker-machine-boot2docker-root-password)
3. [Other possibly useful Docker commands](https://github.com/thinkingserious/flask-microservices-users)
4. Use git-bash with "winpty" to run interactive docker session: `winpty docker exec -it`

# PyCharm
1. [Add additional paths to interpreter, so that it sees the "project" folder of
different services.](https://stackoverflow.com/questions/17198319/how-to-configure-custom-pythonpath-with-vm-and-pycharm)

# Comments to certain parts
### Part 2, Chapter 8
1. Exclude second volume ('/usr/src/app/node_modules') from `docker-compose-dev.yml` to make things work.  
It is a workaround. Normally it should work.
But `npm install` is not installing `fork-ts-checker-webpack-plugin` in the Docker container.

# Other
1. [`docker exec` in git-bash on Windows](https://stackoverflow.com/questions/48001082/oci-runtime-exec-failed-exec-failed-executable-file-not-found-in-path)
2. Use `CMD tail -f /dev/null` in the Dockerfile to be able to run the container indefinitely.