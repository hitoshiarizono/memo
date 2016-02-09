
# Install Docker

## Add the yum repo

```bash
$ sudo tee /etc/yum.repos.d/docker.repo <<-'EOF'
[dockerrepo]
name=Docker Repository
baseurl=https://yum.dockerproject.org/repo/main/centos/$releasever/
enabled=1
gpgcheck=1
gpgkey=https://yum.dockerproject.org/gpg
EOF
```

## Install the Docker package

```bash
$ sudo yum install docker-engine
```

## Start the Docker daemon

```bash
$ sudo service docker start
```

## Verify docker is installed

```bash
$ sudo docker run hello-world
```

