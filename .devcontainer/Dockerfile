# Use the official Dart image as a base
FROM dart:stable

# Install additional packages
RUN apt-get update && apt-get install -y \
  curl \
  git \
  unzip \
  xz-utils \
  zip \
  libglu1-mesa \
  && apt-get clean

# Install Flutter
RUN git clone https://github.com/flutter/flutter.git /opt/flutter \
  && /opt/flutter/bin/flutter doctor

# Add Flutter to PATH
ENV PATH="/opt/flutter/bin:/opt/flutter/bin/cache/dart-sdk/bin:$PATH"

# Set working directory
WORKDIR /workspace

# Run flutter doctor to download dependencies
RUN flutter precache
