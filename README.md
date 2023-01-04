# Docker development environment

## Important notes:
* The data within each container and the database container does not persist, when the stack is removed! **For development save changes using a version control system and export data and results!**
* Alternatively, you can mount persistent folders of the hosts computers file system into the containers by modifying the YAML-files like [this](https://docs.docker.com/storage/bind-mounts/#use-a-bind-mount-with-compose).

## JupyterLab and RStudio
The following runs the JupyterLab and RStudio containers including a MariaDB SQL database server (without GPU enabled) for TensorFlow and general R pipelines
* Install the [Docker engine](https://docs.docker.com/engine/install/) or [Docker Desktop](https://www.docker.com/products/docker-desktop/) (be aware of the license requirements!)
* Start with: `docker-compose -f dev-stack.yml up -d`
* Then, open on the local host
  * **RStudio**: [http://localhost:9090/](http://localhost:9090/) (user: rstudio, password: test123; change in dev-stack.yml!)
  * **JupyterLab**: [http://localhost:9090/](http://localhost:10000/) (you can find the token by running `docker exec -it [CONTAINER ID] jupyter server list` on the jupyter-lab container.
* Shutdown with: `docker-compose -f dev-stack.yml down`
  
## JupyterLab and RStudio with GPU acceleration
The following runs the JupyterLab and RStudio containers including a MariaDB SQL database server with GPU enabled for TensorFlow and general R pipelines
* Setup for GPU support using NVIDIA CUDA compatible images and GPUs:
  * Installation guide for [Linux/Docker-engine with CUDA support](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#installation-guide)
  * Installation on Windows 10/11 with WSL and Docker Desktop:
    * Install [WSL2](https://learn.microsoft.com/de-de/windows/wsl/install)
    * Install [Docker Desktop](https://www.docker.com/products/docker-desktop/) (be aware of the license requirements!)
    * Install [Nvidia drivers for Windows](https://www.nvidia.com/download/index.aspx)
* Start with GPU support `docker-compose -f dev-stack-gpu.yml up -d` (this requires an NVIDIA GPU and the respective drivers/installation)
* Then, open on the local host
  * **RStudio**: [http://localhost:9090/](http://localhost:9090/) (user: rstudio, password: test123; change in dev-stack.yml!)
  * **JupyterLab**: [http://localhost:9090/](http://localhost:10000/) (you can find the token by running `docker exec -it [CONTAINER ID] jupyter server list` on the jupyter-lab container.
* Shutdown with: `docker-compose -f dev-stack-gpu.yml down`
  
## The django stack
The following runs the JupyerLab and RStudio containers for developing Django web apps including a MariaDB server.
* Install the [Docker engine](https://docs.docker.com/engine/install/) or [Docker Desktop](https://www.docker.com/products/docker-desktop/) (be aware of the license requirements!)
* Start with: `docker-compose -f dj-tf-notebook/dev-stack.yml up -d`
* Then, open on the local host to run
  * **RStudio**: [http://localhost:9090/](http://localhost:6060/) (user: rstudio, password: test123; change in dev-stack.yml!)
  * **JupyterLab**: [http://localhost:9090/](http://localhost:7070/) (you can find the token by running `docker exec -it [CONTAINER ID] jupyter server list` on the jupyter-lab container.
  * **Django development server**: run `python manage.py runserver 0.0.0.0:8000` in the JupyerLab terminal and open [http://localhost:9090/](http://localhost:5050/)
* Shutdown with: `docker-compose -f dj-tf-notebook/dev-stack.yml down`
