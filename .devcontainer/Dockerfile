FROM python:3.12-slim

# This Dockerfile adds a non-root user with sudo access. Use the "remoteUser"
# property in devcontainer.json to use it. On Linux, the container user's GID/UIDs
# will be updated to match your local UID/GID (when using the dockerFile property).
# See https://aka.ms/vscode-remote/containers/non-root-user for details.
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID


# 避免在安裝過程中出現交互提示
ENV DEBIAN_FRONTEND=noninteractive

# 安裝基本工具和依賴
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    curl \
    wget \
    build-essential \
    ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 創建非 root 用戶
RUN groupadd --gid 1000 vscode \
    && useradd --uid 1000 --gid 1000 -m vscode \
    && mkdir -p /home/vscode/.vscode-server /home/vscode/.vscode-server-insiders \
    && chown -R vscode:vscode /home/vscode

# 安裝 uv
RUN curl -sSf https://astral.sh/uv/install.sh | sh

# 使用 uv 安裝 Python 開發工具
RUN uv pip install ruff pytest pytest-cov mypy ipykernel black isort pre-commit

# 設置工作目錄
WORKDIR /workspace

