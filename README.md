# Docker development environment

## JupyterLab and RStudio
The following runs the JupyterLab and RStudio containers including a MariaDB SQL database server with GPU enabled for TensorFlow and general R pipelines
* Start with: `docker-compose -f dev-stack.yml up -d`
* Then, open on the local host
  * **RStudio**: [http://localhost:9090/](http://localhost:9090/) (user: rstudio, password: test123; change in dev-stack.yml!)
  * **JupyterLab**: [http://localhost:9090/](http://localhost:10000/) (you can find the token by running `docker exec -it [CONTAINER ID] jupyter server list` on the jupyter-lab container.
* Shutdown with: `docker-compose -f dev-stack.yml down`
  
## The django stack
The following runs the JupyerLab and RStudio containers for developing Django web apps including a MariaDB server.
* Start with: `docker-compose -f dj-tf-notebook/dev-stack.yml up -d`
* Then, open on the local host to run
  * **RStudio**: [http://localhost:9090/](http://localhost:6060/) (user: rstudio, password: test123; change in dev-stack.yml!)
  * **JupyterLab**: [http://localhost:9090/](http://localhost:7070/) (you can find the token by running `docker exec -it [CONTAINER ID] jupyter server list` on the jupyter-lab container.
  * **Django development server**: run `python manage.py runserver 0.0.0.0:8000` in the JupyerLab terminal and open [http://localhost:9090/](http://localhost:5050/)
* Shutdown with: `docker-compose -f dev-stack.yml down`
