# Nginx_RTMP-to-HLS-DockerImage

This is the setup for an nginx container that will receive an rtmp stream, restreams it as HLS(hosted at C:/streamServer/hls) and hosts an html page that shows the HLS stream on localhost:8080. Bellow are the commands that I used to create the image and then the container.

# command to make the image from dockerfile:

docker build -t nginxstream .

# Docker command to start container from imgage:

docker run -d -p 1935:1935 -p 8080:8080 -v C:/streamServer/hls:/tmp/hls --memory=3g --name rtmp_server nginxstream
