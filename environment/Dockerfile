# hash:sha256:ea9e44dda2647b0f1324cc9879d1375af552b155b5af2649c3ff328908256411
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:23.1.0-4-python3.10.12-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-askpass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential=12.9ubuntu3 \
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

COPY postInstall /
RUN /postInstall
