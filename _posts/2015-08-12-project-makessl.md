---
categories: []
title: 'Project:  Makessl'
slug: 'project: makessl' 
created: 1439351078
---
Makessl is a Makefile for GNU make that assists you in generating SSL keys, certificate requests, and (optionally) certificates.

Using it is as simple as:

     git clone https://github.com/deweysasser/makessl
     cd makessl
     vi ssl-data.txt # set the certificate data to your own information
     mkdir -p hosts/www.example.com
     make

The result is that an RSA key and certificate request will be left in that subdirectory.  If, instead of 'make', you use:

     make certs

It will create a CA key and a certificate for you.  This, for example, is terribly useful for maintaining OpenVPN certificates -- just give the ovpn server the root CA and chain and then make client certs with abandon!

Project is available on Github at:  [https://github.com/deweysasser/makessl](https://github.com/deweysasser/makessl)
