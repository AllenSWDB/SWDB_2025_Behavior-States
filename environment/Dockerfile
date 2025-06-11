# hash:sha256:f8d8b3bb761184d71c28f1ba40f41fafe7589fdf5d43db6cd37715595660270a
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:23.1.0-4-python3.10.12-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential \
    && rm -rf /var/lib/apt/lists/*

RUN conda install -y \
        jupyterlab==4.4.3 \
    && conda clean -ya

RUN pip install -U --no-cache-dir \
    dynamax[notebooks]==1.0.1 \
    ipykernel==6.29.5 \
    matplotlib==3.10.3 \
    pandas==2.3.0 \
    pynwb==3.0.0
