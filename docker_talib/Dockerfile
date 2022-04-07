FROM jupyter/datascience-notebook

LABEL maintainer="Danilo Delizia<ddelizia@gmail.com>"
# inspiré de https://raw.githubusercontent.com/ddelizia/jupyter-ta/master/docker/Dockerfile

USER root

RUN wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz && \
    tar xvfz ta-lib-0.4.0-src.tar.gz && \
    cd ta-lib  && \
    ./configure --prefix=/usr  && \
    make  && \
    make install && \
    rm /home/jovyan/ta-lib-0.4.0-src.tar.gz && \
    rm -Rf /home/jovyan/ta-lib

RUN apt-get update

USER $NB_USER

RUN pip install ta-lib
RUN pip install backtrader
#RUN pip install zipline
#RUN pip install enigma-catalyst
#RUN pip install BeautifulSoup4
#RUN pip install tweepy
#RUN pip install praw
#RUN pip install textblob
#RUN pip install quandl
#RUN pip install plotly
#RUN pip install cufflinks
#RUN pip install git+https://github.com/oanda/oandapy.git
#RUN pip install ccxt

# Install Tensorflow


