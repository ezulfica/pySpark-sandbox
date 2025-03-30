FROM python:3.11-slim-bullseye

# Set working directory
WORKDIR /workspace/

COPY . /workspace/

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
      sudo \
      curl \
      vim \
      unzip \
      rsync \
      openjdk-11-jdk \
      build-essential \
      software-properties-common \
      ssh \
      git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Install uv 
RUN curl -LsSf https://astral.sh/uv/install.sh | sh && \
    ln -s ~/.local/bin/uv /usr/local/bin/uv

# Set default path to the virtual environment
ENV PATH="/workspace/.venv/bin:$PATH"
ENV VIRTUAL_ENV="/workspace/.venv"

# Default command (keeps the container running)
CMD ["tail", "-f", "/dev/null"]



