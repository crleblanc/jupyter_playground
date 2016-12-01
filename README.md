# Jupyter Playground

A random collection of Jupyter/IPython notebooks

## Running these notebooks

Installing Python dependencies with easy_install/pip/conda/etc can be 
painful and time consuming especially when there are C extensions. 
Virtual_env can help but can also make life hard.  Docker makes life 
much easier.  I've forked the jupyter/docker-stacks repo on GitHub and 
added obspy for Python 2 and 3: https://github.com/crleblanc/docker-stacks.

There's no need to clone this repo unless you wish to modify the containers.
You can simply pull and run the docker container instead.  Once you've 
installed Docker on your computer (see http://www.docker.io) Pull the 
container with the command:

`docker pull crleblanc/obspy-notebook`

Run the container running the command:
 
`docker run -p 8888:8888 -it crleblanc/obspy-notebook`.

More advanced options: 
https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook.

This command will start the Jupyter notebook which will be available on
localhost, TCP port 8888.  Open a browser to http://localhost:8888 and
you should be able to interact with Jupyter as if it were running on your
host.

You can use the following command to mount your current working directory
on your host as the default working directory on the container 
(/home/jovyan/work).  This read and write files to your host system from
the docker container.  These files will remain intact even if you stop the
docker container.

`docker run -v $(pwd):/home/jovyan/work -p 8888:8888 -it crleblanc/obspy-notebook:latest`