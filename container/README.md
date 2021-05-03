
To build the container you can do the following, change myrepository to be your container repository and port:

docker build . -t myrepository/myfluentd:latest \
  && docker push myrepository/myfluentd:latest


If you are using Centos8 you may to use the following instead:

podman build . -t myrepository/myfluentd:latest \
  && podman push myrepository/myfluentd:latest
