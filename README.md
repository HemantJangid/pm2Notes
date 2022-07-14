# PM2 NOTES

PM2 is an acronym of Process Management Module which is used to run and manage Node. js applications. It's an open-source with an in-built load balancer. When a process goes down, PM2 will automatically restart the service and make it Live. PM2 works on Linux, Windows, and macOS. Although it can be used for application apart from node as well.

## INSTALL

To install pm2 you need to have node and npm already installed on your system.
After that to install pm2 run

```
npm i -g pm2
pm2 -version
```

## COMMANDS

Create a normal node js application to test these commands.

### NORMAL COMMANDS

- `pm2 start app.js` starting an application using filename
- `pm2 status` shows status of all pm2 processes
- `pm2 list` shows status of all pm2 processes
- `pm2 logs process_id/process_name` logs of specified process
- `pm2 delete pid/pname` delete of specified process
- `pm2 start fileName --name nameForTheProcess` starts a new application with specified process name
- `pm2 restart pid/pname` restarts the specified process - it stops the process and starts it again
- `pm2 reload pid/pname` reloads the specified process - it starts a new process and once it is available only then the previous process is deleted
- `pm2 stop pid/pname` stops the specified process
- `pm2 start pid/pname` starts the specified process
- `pm2 restart all` applied the specified command on all processes
- `pm2 monit` starts a terminal gui to monitor all the processes and metadata

### USING ENVIRONMENT VARIABLES WITH PM2

To specify environment variables syntax is `envrionmentVariable pm2 start app.js`. example -

- `PORT=3000 pm2 start app.js` starts the application with provided environment variables

you can also provide environment variables using a config file based on the `sample-config.json` available in this repo

different keys in json file are -

- `name` name of the process
- `cwd` the direct of the app.js file or the file you want to run
- `script` the script file you want to run ex- app.js
- `env` object for all the environment variables you want to use

- `watch` boolean value to turn on and off watch mode
  Watch mode checks if any changes are made in the application code and reloads automatically
  By default the watch mode is off
  Make sure to delete and restart the processes if you make changes to the config file

- `ignore_watch` array with folders names that you want the pm2 to stop watching ex- node_modules
