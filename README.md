# Docker Image

To create docker image dockerfile is needed, a sample dockerfile from which you
can create docker images.

## Create image with dockerfile

To build a docker image run `docker build . `  at the directory your dockerfile
is in searches for a dockerfile in the run directory, creates a docker image
from found dockerfile can give name to image with
`-t {image-name}`, `docker build -t {image-name} . `

## Run image in container

`docker run`, creates an instance of docker image and runs it in a container
adding args at the end of the run command will run those arguments. You can
pass commands as arguments.

`docker run {image-name} args`

## Persisting Data 

To bind a host directory to container use docker run with
`-v absolutepath:containerpath`.

`docker run -v {absolutepath}:{containerpath} {image-name} args`

Changes made in this folder by the container persists, you can observe the
changes in host folder. To get the output of cli image running in container in
host folder set the output as the container folder that is bound to host folder

`docker run --rm -v ${PWD}/host-output:/container-output args -o /container-output`