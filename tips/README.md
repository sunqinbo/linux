# Some Tips

## Add epel repo

```
yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
```

## Add git repo

```
# /etc/yum.repos.d/git.repo

[git]
name=Git Packages for Enterprise Linux 7 - $basearch
baseurl=http://opensource.wandisco.com/centos/7/git/x86_64/
enabled=1
gpgcheck=0
```

## Install Docker

```
wget -O /etc/yum.repos.d/docker-ce.repo https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce
```

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
apt install docker-ce
```

```
vim /etc/docker/daemon.json
{
  "log-driver": "journald",
  "exec-opts": ["native.cgroupdriver=systemd"]
}

{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m",
    "max-file": "3"
  },
  "registry-mirrors": []
}
```
