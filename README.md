# docker_templates
These docker images are for providing a consistent environment for developing and testing software programs at the 4DN DCIC.

## Currently available images
* `4dndcic/ubuntu16.4-r3.5:v1` : Works for Rpairix development/test
* `4dndcic/ubuntu16.4-miniconda-python37:v1` : Works for conda installation test for Pairix
* `4dndcic/ubuntu16.4-python35-pip19:v1` : Works for pypairix test

## To use an image:
```
docker run -it 4dndcic/$DIRNAME:$VERSION
# (`bash` is the default command)
```

## To build and push an image (plesae do not overwrite):
```
DIRNAME=ubuntu16.4-r3.5
VERSION=v1
docker build -t 4dndcic/$DIRNAME:$VERSION $DIRNAME
docker push 4dndcic/$DIRNAME:$VERSION
```
