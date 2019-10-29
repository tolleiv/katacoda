# Layers in docker image
Each Docker image references a list of read-only layers that represent filesystem differences.

Layers are stacked on top of each other to form a base for a container's root filesystem.

Pull debian image to your local system. `docker pull debian.`{{execute}}
`docker history debian`{{execute}} shows you list of layers that debian image contains.

More Information you can find out with: `docker inspect debian`{{execute}}