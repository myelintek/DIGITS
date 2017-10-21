FROM myelintek/caffe:cuda9-cudnn7-v0.16.4
MAINTAINER simon.s.chuang@gmail.com


ARG DIGITS_VERSION=master
ENV DIGITS_VERSION=${DIGITS_VERSION}

ENV DIGITS_ROOT=/opt/digits

RUN git clone -b ${DIGITS_VERSION} https://github.com/myelintek/DIGITS.git ${DIGITS_ROOT} && \
    pip install --upgrade pip && \
    pip install -r ${DIGITS_ROOT}/requirements.txt && \
    pip install scikit-image==0.13.1 && \
    pip install -e $DIGITS_ROOT

CMD python -m digits
