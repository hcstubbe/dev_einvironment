FROM rocker/rstudio:latest

# Install MySQL and oher reuired dependencies
RUN apt-get update -qq && \
    apt-get -y --no-install-recommends install \
    libmysqlclient-dev libxml2-dev

# install required R packages 
# (change it dependeing on the packages you need)

RUN R -e "install.packages(c('shiny'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('shinyWidgets'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('shinydashboard'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('flexdashboard'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('shinyjs'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('shinyvalidate'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('shinyMobile'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('DT'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('kableExtra'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('DBI'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('RMariaDB'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('pool'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('tidyverse'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('readxl'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('openxlsx'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('uuid'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('pwr'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('ggsignif'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('ggpubr'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('effsize'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('cowplot'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('knitr'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('cowplot'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('corrplot'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('psych'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('factoextra'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('janitor'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('parallel'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('RColorBrewer'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('remotes'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('markdown'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('devtools'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('rhub'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('apexcharter'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('fmsb'), repos='http://cran.rstudio.com/')" 
RUN R -e "remotes::install_github('RinteRface/charpente', repos='http://cran.rstudio.com/')" 

EXPOSE 8787

CMD ["/init"]