## Building the Parallel Computing eBook Environment
### Follow these instructions to create a dockerized environment for the Parallel Programming eBook.

#### Prepare your system
Install [Docker](https://docs.docker.com/engine/install/). Follow platform specific instructions for Docker Engine (and Docker Desktop). 

#### Build Docker image
In the root folder of this repo, run the following command to build the Docker image:

```bash
docker build . -t pp.ebook

```

#### Run Docker container
Make sure Docker Engine is running. In the root folder of this repo, run the following commands to startup the Docker container:

```bash
cd ./environment && docker run -i -t --mount type=bind,source="/$(pwd)"/../ebook,target=/home/jupyteruser/ebook -p8888:8888 pp.ebook2024

```

#### Run JupyterLab inside container
You should be in container, with the command-line prompt looking like `jupyteruser@450abc25c0ae:~$`. Run the following commands to startup JupyterLab:

```bash
cd ebook && jupyter lab --ip 0.0.0.0 

```

You will likely have to use the URL starting with `http://127.0.0.1`

#### Exiting the environment
Just <kbd>Ctrl</kbd> + <kbd>C</kbd> to exit JupyterLab, then `exit` to exit the Docker container.