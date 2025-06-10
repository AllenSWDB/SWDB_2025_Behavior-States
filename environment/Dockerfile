# hash:sha256:7e75793acc9514b05f14f5d3617de061419bb64ab182110761b2b48d3b6f0496
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/c1-vscode:4.20.0-pylint2023.10.1-copilot1.143.601

ARG DEBIAN_FRONTEND=noninteractive

ARG GIT_ASKPASS
ARG GIT_ACCESS_TOKEN
COPY git-askpass /

RUN pip install -U --no-cache-dir \
    dynamax[notebooks]==1.0.1 \
    ipykernel==6.29.5 \
    matplotlib==3.10.3 \
    pandas==2.3.0 \
    pynwb==3.0.0
