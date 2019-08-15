# Jenkins

Note reference documentation can be found [here](https://github.com/jenkinsci/docker/blob/master/README.md)

```bash
docker volume create jenkins-lts-vol && \
docker pull jenkins/jenkins:lts && \
docker run \
    --name jenkins-lts \
    --restart=always \
    -p 8080:8080 \
    -p 50000:50000 \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v jenkins_home:/var/jenkins_home \
    jenkins/jenkins:lts
```

password can be found here:

```bash
/var/jenkins_home/secrets/initialAdminPassword
```

```bash
docker run \
    --name jenkins-lts \
    --restart=always \
    -it \
    -p 8080:8080 \
    -p 50000:50000 \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v jenkins-lts-vol:/data/ \
    -e LOG_LEVEL=debug \
    jenkins/jenkins:lts
```

docker volume create jenkins-evergreen-data && \
docker pull jenkins/evergreen:docker-cloud && \
docker run \
    --name evergreen \
    --restart=always \
    -it
    -p 8080:80
    -v /var/run/docker.sock:/var/run/docker.sock
    -v jenkins-evergreen-data:/evergreen/data/
    -e LOG_LEVEL=debug
    jenkins/evergreen:docker-cloud

