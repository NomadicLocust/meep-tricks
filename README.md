# Meep Tips and Tricks
Helpful Tricks for Running Meep (and other) Simulations Effectively

### Command-Line

Start simulation running in the background
```sh
$ nohup meep file.ctl | tee file.out &
```

Find PID (process ID) for your Meep instance
```sh
$ ps -ef | grep meep
```

The above command will list all Meep instances and the command itself. To quickly find the PID when only one Meep process is running, the below command will output it without listing its own PID.
```sh
$ pgrep meep
```

To [peak into the stream](http://unix.stackexchange.com/a/58601) of the running simulation to check the status, find the PID and use `strace`
```sh
$ strace -p[PID] -s9999 -e write
```
or...
```sh
$ tail nohup.out
```
