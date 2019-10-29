# Run container in foreground
In foreground mode (by default when `-d` is not specified), `docker run` can start the process in the container and attach the console to the process' standard input, output, and standard error. It can even pretend to be a TTY (this is what most command line executables expect) and pass along signals.

`docker run -t -p 80:80 nginx`{{execute}}

To stop it, press <kbd>Ctrl</kbd>+<kbd>C</kbd>s.