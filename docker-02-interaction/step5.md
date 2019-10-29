# Kill a container
Start a new container using `docker run -d -it --name newcounter loodse/counter`{{execute}}.

You can kill a container using `docker kill newcounter`{{execute}}.

The main process inside the container will be sent SIGKILL, or any signal specified with option --signal