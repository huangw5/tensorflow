FROM ubuntu:18.04

ARG BAZEL_VERSION=0.23.2

RUN apt-get update
RUN apt-get install -y --no-install-recommends \
      patch \
      wget \
      unzip \
      uuid \
      python \
      python-pip \
      python-setuptools \
      python3 \
      python3-pip \
      python3-setuptools \
      openjdk-8-jdk-headless

RUN wget -q https://github.com/bazelbuild/bazel/releases/download/$BAZEL_VERSION/bazel-$BAZEL_VERSION-linux-x86_64 \
  && mv bazel-$BAZEL_VERSION-linux-x86_64 /usr/bin/bazel \
  && chmod +x /usr/bin/bazel

RUN pip install keras_applications==1.0.4 --no-deps && \
  pip install keras_preprocessing==1.0.2 --no-deps && \
  pip install h5py==2.8.0 && \
  pip install grpcio && \
  pip install wheel && \
  pip3 install keras_applications==1.0.4 --no-deps && \
  pip3 install keras_preprocessing==1.0.2 --no-deps && \
  pip3 install h5py==2.8.0 && \
  pip3 install grpcio && \
  pip3 install wheel

# To pass check in configure.py that python exists in the PYTHON_BIN_PATH
RUN mkdir -p /opt/python3.6/bin/ && ln -s /usr/bin/python3 /opt/python3.6/bin/python3
