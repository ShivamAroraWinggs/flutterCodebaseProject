# Base image
FROM ubuntu:20.04

# Install required dependencies
RUN apt-get update && apt-get install -y \
  curl \
  git \
  unzip \
  zip \
  xz-utils \
  libgtk-3-dev \
  libgl1-mesa-dev \
  libxi6 \
  libxrandr2 \
  libx11-xcb1 \
  libdbus-1-3 \
  build-essential \
  openjdk-11-jdk \
  && apt-get clean

# Install Flutter
RUN git clone https://github.com/flutter/flutter.git /opt/flutter
ENV PATH="/opt/flutter/bin:/opt/flutter/bin/cache/dart-sdk/bin:$PATH"

# Install required Flutter dependencies
RUN flutter doctor --android-licenses || true \
  && flutter config --enable-windows-desktop \
  && flutter precache

# Set working directory
WORKDIR /workspace
