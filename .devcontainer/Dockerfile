FROM golang:1.24-bullseye

# Install necessary tools explicitly
RUN apt-get update && apt-get install -y \
    git \
    build-essential \
    pkg-config \
    libdbus-1-dev \
    libsecret-1-dev \
    libglib2.0-dev \
    curl \
    bash \
    vim \
    nano \
    && rm -rf /var/lib/apt/lists/*

# Install Docker CLI explicitly (for testing/building purposes)
RUN curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh && rm get-docker.sh

# Set up the workspace explicitly
WORKDIR /workspace

# Clone the proton-bridge repo explicitly into workspace
RUN git clone https://github.com/rianrizvi/proton-bridge.git proton-bridge

# Set default directory explicitly
WORKDIR /workspace/proton-bridge

# Expose ports explicitly for Proton Bridge SMTP/IMAP
EXPOSE 1025 1143

# Proton bridge build explicitly (run manually in container terminal when ready):
#   make build-nogui
