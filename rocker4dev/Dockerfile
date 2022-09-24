FROM rocker/rstudio:latest

# Install MySQL and oher reuired dependencies
RUN apt-get update -qq && \
    apt-get -y --no-install-recommends install \
    libmysqlclient-dev libxml2-dev libxt6 default-jre

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
RUN R -e "install.packages(c('RSQLite'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('glue'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('h2o'), repos='http://cran.rstudio.com/')" 
RUN R -e "install.packages(c('ggVennDiagram'), repos='http://cran.rstudio.com/')"
RUN R -e "install.packages(c('BiocManager'), repos='http://cran.rstudio.com/')"
RUN R -e "BiocManager::install('ballgown')"
RUN R -e "BiocManager::install('DRIMSeq')"
RUN R -e "BiocManager::install('DEXSeq')"
RUN R -e "BiocManager::install('stageR')"
RUN R -e "BiocManager::install('GenomicFeatures')"
RUN R -e "BiocManager::install('edgeR')"
RUN R -e "BiocManager::install('GO.db')"
RUN R -e "BiocManager::install('AnnotationDbi')"
RUN R -e "BiocManager::install('goseq')"
RUN R -e "BiocManager::install('org.Hs.eg.db')"
RUN R -e "BiocManager::install('clusterProfiler')"
RUN R -e "BiocManager::install('biomaRt')"
RUN R -e "remotes::install_github('RinteRface/charpente', repos='http://cran.rstudio.com/')" 
RUN R -e "remotes::install_github('pachterlab/sleuth', repos='http://cran.rstudio.com/')"

EXPOSE 8787

CMD ["/init"]