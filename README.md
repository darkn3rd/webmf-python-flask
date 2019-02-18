# **Flask Web Microframework**

## **Running the Application**

These instructions and scripts have been tested on macOS (aka Mac OS X) and Linux with Python installed.

### **Manually with Python**

With [pyenv](https://github.com/pyenv/pyenv) to manage [python](https://www.python.org/) versions, and [virtualenv](https://virtualenv.pypa.io) to isolate your packages, you can optionally create a project area.

```bash
# Optional Setup w/ PyEnv + VirtualEnv
VERSION=$(cat .python-version)
pyenv install $VERSION
pyenv virtualenv $VERSION 'flask-test'
pyenv activate 'flask-test'
# Install Required Packages
pip install -r requirements.txt
# Run Server
./app.py &
# Manually Test
curl -i localhost:5000/
curl -i localhost:5000/hello/Simon
```

### **Using Docker Compose**

```bash
# Start containerized service on Docker
docker-compose up -d
# Determine Guest is native Docker, Docker-Machine or Docker-Desktop
[ -z ${DOCKER_MACHINE_NAME} ] || WEBSERVER=$(docker-machine ip ${DOCKER_MACHINE_NAME})
WEBSERVER=${WEBSERVER:-localhost}
# Manually Test
curl -i $WEBSERVER:5000/
curl -i $WEBSERVER:5000/hello/Simon
```

### **Using Docker on Vagrant/Virtualbox**

```bash
# Start containerized service on Vagrant/Virtualbox guest
vagrant up
# Manually Test
curl -i localhost:5000/
curl -i localhost:5000/hello/Simon
```

## **Running Automated Tests**

```bash
./test.py
```

## Resources

* Python Web Microframework
    * [Flask](http://flask.pocoo.org/)
* Testing
    * [Testing Flask Applications](http://flask.pocoo.org/docs/1.0/testing/)
    * [Python unittests in Jenkins?](https://stackoverflow.com/questions/11241781/python-unittests-in-jenkins)
* Python Environment
    * [python](https://www.python.org/) - language versions
    * [pyenv](https://github.com/pyenv/pyenv) - manage python versions
    * [virtualenv](https://virtualenv.pypa.io) to isolate packages with both Python 2 and Python 3.