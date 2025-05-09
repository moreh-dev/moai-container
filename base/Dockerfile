# ubuntu
ARG BASE_IMG
FROM ${BASE_IMG}

ARG S6_OVERLAY_VERSION=3.2.1.0

# 2: Stop the container
ENV S6_BEHAVIOUR_IF_STAGE2_FAILS=2

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    ca-certificates \
    curl \
    xz-utils \
    vim \
    && rm -rf /var/lib/apt/lists/*

RUN curl -fsSLO https://github.com/just-containers/s6-overlay/releases/download/v${S6_OVERLAY_VERSION}/s6-overlay-noarch.tar.xz \
    && curl -fsSLO https://github.com/just-containers/s6-overlay/releases/download/v${S6_OVERLAY_VERSION}/s6-overlay-x86_64.tar.xz \
    && tar -C / -Jxpf s6-overlay-noarch.tar.xz \
    && tar -C / -Jxpf s6-overlay-x86_64.tar.xz \
    && rm s6-overlay-noarch.tar.xz \
    && rm s6-overlay-x86_64.tar.xz

ENTRYPOINT [ "/init" ]
