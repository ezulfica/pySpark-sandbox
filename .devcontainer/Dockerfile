FROM python:3.11-slim-bullseye

# Set working directory
WORKDIR /workspace/

COPY . /workspace/

# Install default build
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      sudo \
      curl \
      vim \
      unzip \
      rsync \
      build-essential \
      software-properties-common \
      ssh \
      openjdk-11-jdk \
      git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set Hadoop version
ENV HADOOP_VERSION=3.3.6 
ENV HADOOP_HOME=/usr/local/hadoop
ENV PATH=$HADOOP_HOME/bin:$HADOOP_HOME/sbin:$PATH
ENV LD_LIBRARY_PATH=$HADOOP_HOME/lib/native:$LD_LIBRARY_PATH

# Download and install Hadoop manually
RUN curl -L "https://downloads.apache.org/hadoop/common/hadoop-${HADOOP_VERSION}/hadoop-${HADOOP_VERSION}.tar.gz" \
    | tar -xz -C /usr/local/ && \
    mv /usr/local/hadoop-${HADOOP_VERSION} /usr/local/hadoop

# Install uv 
RUN curl -LsSf https://astral.sh/uv/install.sh | sh && \
    ln -s ~/.local/bin/uv /usr/local/bin/uv

# Set default path to the virtual environment
ENV PATH="/workspace/.venv/bin:$PATH"
ENV VIRTUAL_ENV="/workspace/.venv"

# Default command (keeps the container running)
CMD ["tail", "-f", "/dev/null"]



