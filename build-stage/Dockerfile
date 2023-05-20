FROM python:3.10-slim

LABEL maintainer="VergilGao"
LABEL org.opencontainers.image.source="https://github.com/VergilGao/docker-mdc"
LABEL org.opencontainers.image.description="用于 vergilgao/mdc 的构建层"

RUN apt update && apt install -y  \
    binutils \
    wget && \
    # update pip
    pip install --upgrade pip && \
    pip install pyinstaller

ARG MDC_REQUIREMENTS_SOURCE_VERSION
ENV MDC_REQUIREMENTS_SOURCE_VERSION=${MDC_REQUIREMENTS_SOURCE_VERSION:-master}

# install requirements
RUN cd /tmp && \
    wget -O mdc_requirements.txt https://raw.githubusercontent.com/553531284/Movie_Data_Capture/$MDC_REQUIREMENTS_SOURCE_VERSION/requirements.txt && \
    pip install -r mdc_requirements.txt