FROM jupyter/datascience-notebook

# Install reuired dependencies
RUN apt-get update -qq && \
    apt-get -y --no-install-recommends install \
	libz-dev
	
WORKDIR /app
RUN git clone --recursive https://github.com/nanoporetech/pomoxis \
	cd pomoxis \
	make install \
	. ./venv/bin/activate

WORKDIR /app

EXPOSE 8787

CMD ["/init"]