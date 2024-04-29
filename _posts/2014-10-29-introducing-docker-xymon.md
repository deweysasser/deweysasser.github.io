---
excerpt: "In short:  build and deploy this for instant monitoring.\r\n\r\nSeeing no
  viable containerization of the Xymon monitoring system (and the 'net is large --
  I could have missed it), I have created some.\r\n\r\nEventually I will be maintaining
  images on the Docker Hub as well as the source.\r\n\r\nFor now, get it from https://github.com/deweysasser/docker-xymon\r\n\r\n\r\nHere's
  the README...\r\n\r\n"
categories:
- software
- docker
- docker-xymon
title: Introducing docker-xymon
slug: introducing docker-xymon 
created: 1414595394
---
In short:  build and deploy this for instant monitoring.

Seeing no viable containerization of the Xymon monitoring system (and the 'net is large -- I could have missed it), I have created some.

Eventually I will be maintaining images on the Docker Hub as well as the source.

For now, get it from https://github.com/deweysasser/docker-xymon


Here's the README


docker-xymon
============

Dockerization of the Xymon monitoring system on an Ubuntu base

Example
=======

    docker build -t xymon docker-xymon
    docker run -d -p 80:80 -p 1984:1984 -v /etc/xymon:/etc/xymon --name xymon xymon

Interface
=========

Ports
-----

* 80 -- Web server
* 1984 -- Xymon/bb client reporting port

Volumes
-------

* /etc/xymon -- all xymon configuration data
* /var/lib/xymon -- xymon data (monitoring state)


Known Issues
============

* Password protection on cgi directories is currently disabled
* There is no way for Xymon to send email

Maintainer
==========

Please submit all issues/suggestions/bugs via
https://github.com/deweysasser/docker-xymon
