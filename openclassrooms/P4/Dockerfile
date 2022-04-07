ARG BASE_CONTAINER=jupyter/minimal-notebook
FROM $BASE_CONTAINER
LABEL author="Shinichi Okada"
USER root
RUN pip install pandas numpy matplotlib plotly sklearn seaborn xgboost folium 

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_UID


