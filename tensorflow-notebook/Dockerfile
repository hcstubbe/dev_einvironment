# Basis-Image von jupyter/tensorflow-notebook
FROM jupyter/tensorflow-notebook

# Benutzer root für die Installation von Paketen
USER root

# Aktualisieren und Installieren der benötigten Pakete
RUN apt-get update && \
    apt-get install -y samtools minimap2 hisat2 wget && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install StringTie v2.2.3
RUN wget https://github.com/gpertea/stringtie/releases/download/v2.2.3/stringtie-2.2.3.Linux_x86_64.tar.gz && \
    tar -xzf stringtie-2.2.3.Linux_x86_64.tar.gz && \
    mv stringtie-2.2.3.Linux_x86_64/stringtie /usr/local/bin/ && \
    rm -rf stringtie-2.2.3.Linux_x86_64 stringtie-2.2.3.Linux_x86_64.tar.gz

# Zurück zum Standardbenutzer
USER ${NB_UID}