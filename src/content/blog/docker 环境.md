---
title: "一个完美的 docker 环境"
description: "一个完美的 docker 环境。"
pubDate: 2026-06-17
tags: ["docker"]
---

```bash
# 1. 系统工具
apt update && apt install -y vim wget curl git htop tmux zip unzip p7zip-full net-tools iputils-ping rsync build-essential cmake ffmpeg git-lfs pip npm socat iproute2

# 2. 初始化 Git LFS
git lfs install

# 3. 优化 pip 体验
echo 'export PIP_ROOT_USER_ACTION=ignore' >> ~/.bashrc
source ~/.bashrc
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
pip config set global.trusted-host pypi.tuna.tsinghua.edu.cn

# 4. 安装 Python 核心库
pip install --upgrade pip
pip install numpy pandas scipy scikit-learn matplotlib seaborn tqdm ipython jupyter transformers datasets accelerate peft trl tokenizers safetensors bitsandbytes tensorboard einops timm

# 5. 安装 nodejs 需要外网环境 node -v npm -v验证
curl -fsSL https://fnm.vercel.app/install | bash
source ~/.bashrc
fnm use --install-if-missing 22

npm i -g @anthropic-ai/claude-code@latest
npm i -g @openai/codex@latest
npm i -g @google/gemini-cli@latest

curl -fsSL https://github.com/SaladDay/cc-switch-cli/releases/latest/download/install.sh | bash
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

curl -fsSL https://code-server.dev/install.sh | sh

```

保存为新镜像：

```
docker commit my_cuda12_dev my_ai_env:v1
```

