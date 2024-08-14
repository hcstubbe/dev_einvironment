# Basis-Image von jupyter/tensorflow-notebook
FROM jupyter/tensorflow-notebook

# Benutzer root für die Installation von Paketen
USER root

# Aktualisieren und Installieren der benötigten Pakete
RUN apt-get update && \
    apt-get install -y samtools minimap2 hisat2 stringtie && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Zurück zum Standardbenutzer
USER ${NB_UID}