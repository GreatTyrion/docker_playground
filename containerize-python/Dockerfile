FROM ubuntu:18.04

# Update package index and install dependencies
RUN apt-get update && apt-get install -y software-properties-common

# Add deadsnakes PPA for Python 3.10 installation
RUN add-apt-repository -y ppa:deadsnakes/ppa

# Update package index again after adding PPA
RUN apt-get update

# Install Python 3.10 and pip
RUN apt-get install -y python3.10 python3.10-distutils

# Set Python 3.10 as the default Python version
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.10 1

# Install curl for downloading get-pip.py
RUN apt-get install -y curl

# Install pip for Python 3.10
RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && \
    python3.10 get-pip.py && \
    rm get-pip.py

# Set the working directory
WORKDIR /app
