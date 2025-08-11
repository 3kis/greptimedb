FROM ubuntu:24.04

# 设置非交互式安装，避免卡在 tzdata 等提示
ENV DEBIAN_FRONTEND=noninteractive

# 安装基本工具和依赖，包括 bash
RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    libssl-dev \
    pkg-config \
    cmake \
    git \
    bash \
    protobuf-compiler \
    && rm -rf /var/lib/apt/lists/*

# 安装 Rust 工具链
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
ENV PATH="/root/.cargo/bin:${PATH}"

# 验证 protoc 版本
RUN protoc --version
