
# Run an Apache in a Container

For interactive processes (like a shell), you must use `docker` run with `-i -t` together in order to allocate a tty for the container process. `-i -t` is often written `-it`.

To expose a container's internal port, you can start the container with the `-P` or `-p` flag. The exposed port is accessible on the host and the ports are available to any client that can reach the host.

Now start a new container to install Apache trough the package manger - execute:

`docker run -it -p 80:80 alpine`{{execute}}

Now, let's install it:

`apk add --update apache2`{{execute}}

Start the Apache:

`httpd -D FOREGROUND`{{execute}}

Test access to website, got to: https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/