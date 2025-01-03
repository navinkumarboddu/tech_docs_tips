# NODE.JS (18+)
<hr>

This document explains how to install **Node.js 18 or higher** using **NVM (Node Version Manager)**.

SDKMAN does **not** support Node.js as a valid candidate.  
For Node.js, **NVM is the recommended and officially supported tool**.

---

## Prerequisites

- Linux or macOS
- `curl` or `wget`

---

## Install NVM

### Using `curl`
```bash
curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

###  Using wget
```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

### Load NVM (without restarting terminal)
```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

### Verify NVM Installation
```bash
nvm --version
```

### List Available Node.js Versions
```bash
nvm list-remote
```

### Install Node.js 18+
```bash
nvm install 18
```

This installs the latest stable Node.js 18.x version.

### Use Installed Node Version
```bash
nvm use 18
```

### Set Default Node.js Version
```bash
nvm alias default 18
```

### Verify Node.js Installation
```bash
node -v
npm -v
```

### Switch Between Node.js Versions
```bash
nvm install 20
nvm use 20
```

### Uninstall Node.js Version (Optional)
```bash
nvm uninstall 18
```

### Notes

1. NVM is the officially recommended tool for Node.js version management
2. Supports per-project Node versions via .nvmrc
3. Ideal for Angular, React, and backend Node projects
4. Works on Linux, macOS, and WSL