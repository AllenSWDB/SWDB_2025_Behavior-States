# hash:sha256:66d57c9f2fbb4c93dac27fd8077d8787b2f305371b6ef7f8452764fe3be641b7
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/c1-vscode:4.20.0-pylint2023.10.1-copilot1.143.601

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN conda install -y \
        jupyterlab==4.4.3 \
    && conda clean -ya

RUN pip install -U --no-cache-dir \
    dynamax[notebooks]==1.0.1 \
    ipykernel==6.29.5 \
    matplotlib==3.10.3 \
    pandas==2.3.0 \
    pynwb==3.0.0
