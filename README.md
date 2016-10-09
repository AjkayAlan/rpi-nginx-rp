# rpi-nginx-rp
Raspberry Pi Docker image for a NGINX reverse proxy

## Building
Build the container using something like the following:  

`docker build -t ajkayalan/rpi-nginx-rp:latest https://github.com/AjkayAlan/rpi-nginx-rp.git`  

If you have cloned locally, you can do something like the following instead:  

`docker build -t ajkayalan/rpi-nginx-rp:latest .`  

## Running
After building the container, you will want to run it.

First, build a network for anything you want to have reverse proxied:

`docker network create rp`

Then you can run this on that network. Note that this has to be the only thing on port 80/443:

`docker run --name rpi-nginx-rp --net rp -d -p 80:80 -p 443:443 ajkayalan/rpi-nginx-rp:latest`
