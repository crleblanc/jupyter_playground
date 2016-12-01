# Jupyter Playground

A random collection of Jupyter/IPython notebooks

## Downloading these notebooks

Install Git on your system and type the following:

`git clone https://github.com/crleblanc/jupyter_playground.git
cd jupyter_playground`

Alternatively you can download an archive of this repository and unpack 
it on your system.

## Running these notebooks

Installing Python dependencies with easy_install/pip/conda/etc can be 
painful and time consuming especially when there are C extensions. 
Virtual_env can help but can also make life hard.  Docker makes life 
much easier.  I've forked the jupyter/docker-stacks repo on GitHub and 
added obspy for Python 2 and 3: https://github.com/crleblanc/docker-stacks.

There's no need to clone this repo unless you wish to modify the containers.
You can simply pull and run the docker container instead.  Once you've 
installed Docker on your computer (see http://www.docker.io) Pull and run 
the container with the following command.  This will mount your current
working directory as the working directory in the container 
(/home/jovyan/work).  We're using port 8888 to access the web interface.

`docker run -v $(pwd):/home/jovyan/work -p 8888:8888 -it crleblanc/obspy-notebook:latest`

More advanced options: 
https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook.

This reads and writes files to your host system from the docker container. 
These files will remain intact even if you stop the docker container.

This command will start the Jupyter notebook which will be available on
localhost, TCP port 8888.  Open a browser to http://localhost:8888 and
you should be able to interact with Jupyter as if it were running on your
host.

## Security

The above command runs the Jupyter session unencrypted on your local computer.
It's a very good idea to enable authentication and https even if you're running
these notebooks from Docker.  Read this link for more information: 
http://jupyter-notebook.readthedocs.io/en/latest/public_server.html
