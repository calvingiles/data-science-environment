data-science-environment
============

Portable development environment for data analysis

This defines a Dockerfile and related resources for building an ipython notebook server in a docker container capable of connecting to Adthena's databases, queues etc. and performing desired analysis.

## Installing
### Simple first time install

* Set up a [docker account](https://www.docker.com/)
* Install [boot2docker](http://boot2docker.io/)
* Init boot2docker:

```
$ boot2docker init
$ boot2docker start
$ $(boot2docker shellinit)
```

* If you get told to set the environment variables, add the `export` commands to your `bash_profile` (or ask someone who knows how).
* Run the setup script:

```
python <( curl https://gist.githubusercontent.com/calvingiles/FIXME/raw/start_docker_env.py ) -p YourPassword
```

### Update your setup to latest

* Simply re-run the setup command above.


Once the container has been started, navigatge to `http://localhost:443` or, if using boot2docker (i.e. on a mac), get your docker host with `boot2docker ip` and replace `localhost` with that. Login with the password you passed into the `start_ds_notebook.py` script

## Debugging

If you find an error like this:

```
Unable to find image 'calvingiles/data-science-notebook-server' locally
Pulling repository calvingiles/data-science-notebook-server
2014/11/19 12:08:13 Error: image calvingiles/data-science-notebook-server not found
```

then run `docker login` and try the last step again.
