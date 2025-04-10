# Python 3.12 Development Environment

A containerized development environment for Python 3.12 projects with modern development tools.

## 中文說明

這是一個基於 Python 3.12 的開發環境，使用 VS Code 的 Dev Containers 功能，提供隔離且一致的開發體驗。

### 特點

- 基於 Python 3.12 slim 映像
- 使用 uv 作為快速的包管理工具
- VS Code 設置優化了 Python 開發體驗

### 如何使用

1. 安裝 [VS Code](https://code.visualstudio.com/) 和 [Dev Containers 擴展](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
2. 安裝 [Docker Desktop](https://www.docker.com/products/docker-desktop/)
3. 在 VS Code 中打開此項目文件夾
4. 當提示時選擇 "Reopen in Container"，或使用命令面板執行 "Dev Containers: Reopen in Container"

## English Documentation

This is a Python 3.12 development environment using VS Code's Dev Containers feature, providing an isolated and consistent development experience.

### Features

- Based on Python 3.12 slim image
- Uses uv as a fast package manager
- Configured to run as non-root user
  - pre-commit: Git hooks management
- Configured to run as non-root user
- VS Code settings optimized for Python development

### How to Use

1. Install [VS Code](https://code.visualstudio.com/) and the [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
2. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
3. Open this project folder in VS Code
4. When prompted, select "Reopen in Container", or use the command palette to execute "Dev Containers: Reopen in Container"

## Development Workflow

After the container is running:

1. Create your Python files in the workspace
2. VS Code will automatically use the configured linting and formatting tools
3. Install additional packages using uv: `uv pip install package-name`
4. Run tests with pytest: `python -m pytest`

## Container Details

- Base Image: python:3.12-slim
- Package Manager: uv
- Workspace: /workspace