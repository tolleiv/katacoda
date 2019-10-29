# Stop the Container

Exit the process as you normally would do with <kbd>Ctrl</kbd>+<kbd>C</kbd>:

`echo "Send Ctrl+C to Terminal"`{{execute interrupt}}

Exit the shell with <kbd>Ctrl</kbd>+<kbd>D</kbd> or type `exit`{{execute}}.

The container is stopped but it still exists on disk. You can take a look:

`docker ps -a`{{execute}}

To delete all running and stopped container execute:

`docker rm $(docker ps -aq)`{{execute}}

Check if the containers get deleted:

`docker ps -a`{{execute}}

