# FROM myelintek/nvcaffe:cuda9-cudnn7-v0.16.4
# FROM myelintek/tensorflow:v1.4.0-rc0
FROM myelintek/nvcaffe:cuda9-cudnn7-nccl2-v0.16.4
MAINTAINER simon.s.chuang@gmail.com


ARG DIGITS_VERSION=v6.0.1
ENV DIGITS_VERSION=${DIGITS_VERSION}
ENV DIGITS_JOBS_DIR=/data
ENV DIGITS_ROOT=/opt/digits

RUN apt-get update && apt-get install -y --no-install-recommends \
        graphviz \
        python-magic \
        python-tk \
        vim && \
    rm -rf /var/lib/apt/lists/*

RUN git clone -b ${DIGITS_VERSION} https://github.com/myelintek/DIGITS.git ${DIGITS_ROOT} && \
    pip install --upgrade pip && \
    pip install -r ${DIGITS_ROOT}/requirements.txt && \
    pip install scikit-image==0.13.1 opencv-python && \
    pip install -e $DIGITS_ROOT && \
    pip install $DIGITS_ROOT/plugins/data/sunnybrook/

CMD python -m digits
