FROM rocker/rstudio:latest

# Install MySQL dependency
RUN apt-get update -qq && \
    apt-get -y --no-install-recommends install \
    libmysqlclient-dev libxml2-dev

# install required R packages 
# (change it dependeing on the packages you need)
RUN R -e "install.packages(c('shiny', 'shinyWidgets', 'shinydashboard', 'flexdashboard', 'shinyjs', 'shinyvalidate', 'shinyMobile', 'DT', 'kableExtra', 'DBI', 'RMariaDB', 'pool', 'tidyverse', 'readxl', 'openxlsx', 'uuid', 'pwr', 'ggsignif', 'ggpubr', 'effsize', 'cowplot', 'knitr', 'cowplot', 'corrplot', 'psych', 'factoextra', 'janitor', 'parallel', 'RColorBrewer', 'remotes', 'markdown', 'devtools', 'rhub'), repos='http://cran.rstudio.com/')" 

RUN R -e "remotes::install_github('RinteRface/charpente')"


EXPOSE 8787


CMD ["/init"]