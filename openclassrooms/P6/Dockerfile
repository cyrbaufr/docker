ARG BASE_CONTAINER=jupyter/minimal-notebook
ARG $NB_UID=cyril

FROM $BASE_CONTAINER
LABEL author="Shinichi Okada"
USER root
# https://github.com/a5huynh/scrapyd-playground/blob/master/Dockerfile
#	Pillow (Python Imaging Library) dependencies
#		libtiff4-dev libjpeg8-dev zlib1g-dev libfreetype6-dev
# 		liblcms2-dev libwebp-dev tcl8.5-dev tk8.5-dev python-tk
# Voir aussi dockerfile de l'image officielle Pillow
# https://github.com/python-pillow/docker-images/blob/main/ubuntu-20.04-focal-amd64/Dockerfile
RUN apt-get update && apt-get install -y libtiff5-dev \
			libjpeg8-dev zlib1g-dev libfreetype6-dev \
			liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python-tk


RUN pip install pandas numpy matplotlib plotly sklearn \
	seaborn nltk Pillow wordcloud tensorflow-cpu gensim \
	transformers sentencepiece tensorflow_hub tensorflow_text\
	opencv-contrib-python
	
RUN pip3 install ipywidgets

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_UID
