# base
ARG BASE_IMG
FROM ${BASE_IMG}

ARG CODE_SERVER_VERSION=4.99.4

ENV PORT=80

RUN curl -fsSLO https://github.com/coder/code-server/releases/download/v${CODE_SERVER_VERSION}/code-server_${CODE_SERVER_VERSION}_amd64.deb \
    && dpkg -i code-server_${CODE_SERVER_VERSION}_amd64.deb \
    && rm code-server_${CODE_SERVER_VERSION}_amd64.deb

COPY --chmod=755 s6-rc.d /etc/s6-overlay/s6-rc.d

EXPOSE ${PORT}
