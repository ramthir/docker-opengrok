[![Build Status](https://travis-ci.org/sukujgrg/docker-opengrok.svg?branch=master)](https://travis-ci.org/sukujgrg/docker-opengrok)

## docker-opengrok
a container of [OpenGrok](https://github.com/OpenGrok/OpenGrok)

### About [OpenGrok](https://github.com/OpenGrok/OpenGrok)

> OpenGrok is a fast and usable source code search and cross reference engine, written in Java. It helps you search, cross-reference and navigate your source tree

#### Usage

To start this OpenGrok, run
```
docker run -v /home/ubuntu/YOUR_SOURCEDIR:/var/opengrok/src -dit -p HOST_PORT:8080 sukujgrg/opengrok
```

and access it via the following url (see the note)
```
http://HOST_IP:HOST_PORT/source
```

##### Note
OpenGrok analyzes the source tree and builds a search index along with cross-referenced hypertext versions of the source files. The time it takes to build the index is based on the size of your source. You can watch "index"ing status using the below command. **OpenGrok will be avilable on the above mentioned url after "index"ing is finished**.

you can watch "index"ing log by tailing `/var/opengrok/log/opengrok0.0.log`
```
docker exec CONTAINER_ID tail -f /var/opengrok/log/opengrok0.0.log
```
