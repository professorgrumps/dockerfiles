**Table of Contents**

- [dockerfiles](#dockerfiles)
  - [useful docker images](#useful-docker-images)
    - [mongodb / mongo express](#mongodb--mongo-express)
  - [x-images](#x-images)
    - [x-tor](#x-tor)
    - [x-burp](#x-burp)
  - [TODO](#todo)

# dockerfiles
a place to put docker related stuff

## useful docker images
all of these assume docker-machine as a vm on windows.

### mongodb / mongo express
mongodb on :27017

`docker run -tid --name mongo -p 27017:27017 mongo`

mongo-express on http://192.168.99.100:8081

`docker run --name mongo-express -tid --link mongo:mongo -p 8081:8081 mongo-express`

## x-images
the following assumes xserver is running.

 1. cygwin> `xlaunch &`
 2. multiple windows
 3. start no client
 4. disable access control
 2. additional parameters: `-listen tcp`

### x-tor
TOR web browser

`docker run -d -e DISPLAY=192.168.99.1:0 --name x-tor jess/tor-browser`

### x-burp
starts burp suite community edition proxy on http://192.168.99.100:8080

## TODO
- selenium / zalenium
- kali
