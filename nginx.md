
# Install nginx

## Add the yum repo

```bash
$ sudo tee /etc/yum.repos.d/docker.repo <<-'EOF'
[nginxrepo]
name=nginx repo
baseurl=http://nginx.org/packages/centos/$releasever/$basearch/
gpgcheck=0
enabled=1
EOF
```

## Install the Docker package

```bash
$ sudo yum install nginx
```

## Start the Docker daemon

```bash
$ sudo systemctl start nginx
```


