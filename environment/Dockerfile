# hash:sha256:ff80fbe31b5f16550d67ddf5f9adb97dda9a5beb185c10da6bfa9fc6171b4610
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:23.1.0-4-python3.10.12-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
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
