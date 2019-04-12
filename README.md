# docker_templates
These docker images are for providing a consistent environment for developing and testing software programs at the 4DN DCIC.

# Currently available images
* `4dndcic/ubuntu16.4-r3.5:v1` : Works for Rpairix development/test

## To build and push an image:
```
DIRNAME=ubuntu16.4-r3.5
VERSION=v1
docker build -t 4dndcic/$DIRNAME:$VERSION $DIRNAME
docker push 4dndcic/$DIRNAME:$VERSION
```

## To use an image:
```
docker run -it 4dndcic/$DIRNAME:$VERSION
# (`bash` is the default command)
```
