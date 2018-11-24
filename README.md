# **Flask WebMF**

## **Using on Mac OS X Host**

* Prerequisites:
  * Install XCode Command Line Tools
  * Install Brew `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

### **Install**

```bash
$ brew install python
$ # Install/Setup virtualenv (optional)
$ pip install virtualenv
$ pip install virtualenvwrapper
$ mkdir ${HOME}/.virtualenvs
$ source /usr/local/bin/virtualenvwrapper.sh
```

## **Run**

```bash
$ pip install flask # install flask library
$ ./app.py          # run program
```

### **Run Using Virtualenv**

This uses [virtualenv](https://virtualenv.pypa.io/en/latest/), so that libraries are installed in locally in only your account.

```bash
$ mkvirtualenv flaskenv            # create segregated environment
$ pip install -r requirements.txt  # install flask library locally
$ ./app.py                         # run program
$ ## Run Tests Here (see below)
$ deactivate                       # exit segregated environment
```

## **Using Docker or Vagrant**

See [Tools Readme](../TOOLS.md) for more information on install, setup, and start Docker or Vagrant.

### **Build and Run with Docker Compose**

```bash
$ docker-compose up -d
```

### **Build and Run with Vagrant**

```bash
$ vagrant up
```

## **Testing Results**

```bash
$ [ -z ${DOCKER_MACHINE_NAME} ] || WEBSERVER=$(docker-machine ip ${DOCKER_MACHINE_NAME})
$ WEBSERVER=${WEBSERVER:-localhost}
$ PORT=5000
$ curl -i ${WEBSERVER}:${PORT}
HTTP/1.0 200 OK
Content-Type: text/html; charset=utf-8
Content-Length: 13
Server: Werkzeug/0.11.4 Python/2.7.11
Date: Sun, 13 Mar 2016 07:02:41 GMT

Hello World!
```
