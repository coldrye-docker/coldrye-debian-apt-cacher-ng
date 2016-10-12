# coldrye-debian-apt-cacher-ng

[![coldrye/debian-apt-cacher-ng](http://dockeri.co/image/coldrye/debian-apt-cacher-ng)](https://hub.docker.com/r/coldrye/debian-apt-cacher-ng/)


## Description

This packages apt-cacher-ng in various releases based on coldrye/debian-tini.


## Image Releases

Images are released for the following debian releases.

- jessie
- testing

See https://hub.docker.com/r/coldrye/debian-apt-cacher-ng/tags/ for a complete list.


## Volumes

- /etc/apt-cacher/ng
- /var/cache/apt-cacher-ng 


## Command

The command is set to ```/usr/sbin/apt-cacher-ng -c /etc/apt-cacher-ng```.


## Usage

General Usage

```
docker create -v $(pwd)/data/conf:/etc/apt-cacher-ng -v $(pwd)/data/cache:/var/cache/apt-cacher-ng -p 3142:3142/tcp --name aptproxy coldrye/debian-apt-cacher-ng:<TAG>
```

