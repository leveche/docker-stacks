ARG BASE_CONTAINER=jupyter/datascience-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Lev Eche <github+datasci-notebook@semyon.org>"

# Set when building on Travis so that certain long-running build steps can
# be skipped to shorten build time.
ARG TEST_ONLY_BUILD

USER root

# need graphviz
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
       graphviz \
    && /opt/conda/bin/pip install pydotplus \
    && rm -rf /var/lib/apt/lists/*

# Add Live slideshows with RISE
RUN conda install -c damianavila82 rise
RUN conda install -c conda-forge jupyterlab-git

USER $NB_UID

