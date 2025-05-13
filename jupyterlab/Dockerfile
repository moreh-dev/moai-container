# base
ARG BASE_IMG
FROM ${BASE_IMG}

ARG JUPYTERLAB_VERSION=4.4.2

ENV PORT=80

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    python3 \
    python3-pip \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir \
    jupyterlab==${JUPYTERLAB_VERSION}

RUN jupyter labextension disable "@jupyterlab/apputils-extension:announcements"

COPY --chmod=755 s6-rc.d /etc/s6-overlay/s6-rc.d

EXPOSE ${PORT}
