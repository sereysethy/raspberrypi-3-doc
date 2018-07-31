This repository describes step to install and configure [Raspberry Pi 3](https://www.raspberrypi.org/ ) running [RASPBIAN STRETCH LITE](https://www.raspberrypi.org/downloads/raspbian/ ). It details steps to install:

- Configure freshly installed Raspberry Pi
- Enable SSH
- Change locale
- Install `docker` and `docker-compose`
- Development tools such as `git`, `gcc`, etc.

To install raspbian image on SD card, follow this [instruction](https://www.raspberrypi.org/documentation/installation/installing-images/README.md ).

# 1 - Update system

```
sudo apt-get update
sudo apt-get install
```

### Change locale to `en US UTF-8`

```
$ sudo raspi-config"

# choose localse and select en_US.UTF-8
```

### Enable ssh

```
$ sudo raspi-config"

# choose Interface
```

# 2 - Docker

## Install docker

To install docker, just run following script. Sometimes after the installation, it reports some problems. But the installation seems to be complete. Reboot system and try `sudo docker ps`.

```
curl -sSL https://get.docker.com | sh
```

If you would like to use Docker as a non-root user, you should now consider
adding your user to the `docker` group with something like:

```
sudo usermod -aG docker pi
```

## Install docker-compose

Install required packages

```
sudo apt-get install -y python python-pip
```

Install Docker Compose from pip

```
sudo pip install docker-compose # to install globally
```

# 3 - Development

```
sudo apt-get install -y build-essential git python vim
```

# 4 - Python 3

Install `pip3` for `python3`

```
sudo apt-get install python3-pip
```

More info on how to install `python`, [read more](https://www.raspberrypi.org/documentation/linux/software/python.md '')
