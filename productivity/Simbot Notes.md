# Simbot Notes

## Common Struggles

Before anything, make sure you're in the simbot venv.


##### `just debug`

If you get something like:
```bash
just debug
mkdir -p data/db
+ trap 'just debug-shutdown mongod.log data/db; exit' SIGINT
+ mongod --dbpath data/db --fork --logpath mongod.log
about to fork child process, waiting until server is ready for connections.
forked process: 3758
ERROR: child process failed, exited with 1
To see additional information in this output, start without the "--fork" option.
error: Recipe `debug` failed with exit code 1
```

Run `ps ax | grep mongod` and kill the `mongod` process. Then try again.