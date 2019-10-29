# Detached container
To start a container in detached mode, use -d=true or just -d option. By design, containers exit when the root process used to run the container exits.

`docker run -d -t -p 80:80 nginx`{{execute}}

Detaching from a running container
Run a container: `docker run -it --name counter loodse/counter`{{execute}}

It will create and run a new container with name counter from image loodse/counter and will print a a numbers in increasing fashion on screen.

You can detach from this running container using CTRL-p CTRL-q key sequence.

Attaching to running container
You can use docker attach to attach.

Spawn a new container using `docker run -d -it --name counter1 loodse/counter`{{execute}}.

It will start a container in detached mode using -d flag.

You can attach local standard input, output, and error streams to a running container using `docker attach counter1`{{execute}}.

