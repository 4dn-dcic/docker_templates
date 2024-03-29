# docker_templates
These docker images are for providing a consistent environment for developing and testing software programs at the 4DN DCIC.

## Currently available images
* `4dndcic/ubuntu16.04plus:v1` : Ubuntu plus utils like wget, less, bzip2, etc installed
* `4dndcic/ubuntu16.04-r3.5:v1` : Works for Rpairix development/test
* `4dndcic/ubuntu16.04-miniconda-python36:v1` : works for conda installation test for snakemake
* `4dndcic/ubuntu16.04-miniconda-python37:v1` : Works for conda installation test for Pairix
* `4dndcic/ubuntu16.04-python35-pip19:v1` : Works for pypairix test
* `4dndcic/ubuntu16.04-python27-pip19:v1`
* `4dndcic/ubuntu16.04-python36-pip19:v1` : works for tibanna test
* `4dndcic/ubuntu16.04-miniconda-python39-git2.31-mamba:v1` : works for snakemake test
  * `conda 4.10.0`
  * `mamba 0.9.2`
  * `git 2.31.1`
  * `Python 3.9.2`
  * `Cython 0.29.22`

* `4dndcic/ubuntu16.04-miniconda-python36-docker:v1` : docker inside docker (e.g. test for cwl)
  * To use docker inside docker, run it with `privileged`

  ```
  docker run -it --privileged 4dndcic/ubuntu16.04-miniconda-python36-docker:v1
  ```
  Then, inside the container, start docker daemon.
  ```
  service docker start
  ```



## To use an image:
```
docker run -it 4dndcic/$DIRNAME:$VERSION
# (`bash` is the default command)
```

## To build and push an image (plesae do not overwrite):
```
DIRNAME=ubuntu16.04-r3.5
VERSION=v1
docker build -t 4dndcic/$DIRNAME:$VERSION $DIRNAME
docker push 4dndcic/$DIRNAME:$VERSION
```
