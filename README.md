

# Docker Toolbox for Windows configuration
1. [Confiure VirtualBox to have access to the volume folder](https://medium.com/@Charles_Stover/fixing-volumes-in-docker-toolbox-4ad5ace0e572)
    1. Refer to it from docker-compose "volumes" or from docker run "-v" option
    2. Refer just by the name you gave it in the settings (Shared Folders) of VirtualBox
2. [SSH into docker machine as root](https://stackoverflow.com/questions/32646952/docker-machine-boot2docker-root-password)
3. [Other possibly useful Docker commands](https://github.com/thinkingserious/flask-microservices-users)
4. Use git-bash with "winpty" to run interactive docker session: `winpty docker exec -it`