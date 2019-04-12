# docker_templates
These docker images are for providing a consistent environment for developing and testing software programs at the 4DN DCIC.

* example
```
USERNAME=4dn-dcic
DIRNAME=ubuntu16.4-r3.5
VERSION=v1
docker build -t $USERNAME/$DIRNAME:$VERSION $DIRNAME
docker push $USERNAME/$DIRNAME:$VERSION
```
