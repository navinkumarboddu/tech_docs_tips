# ANGULAR CLI (18+)
<hr>

This document explains how to install **Angular CLI 18 or higher**.

Angular CLI is installed using **npm**.  
SDKMAN does **not** support Angular CLI as a valid candidate.

---

## Prerequisites

- Linux or macOS
- Node.js **18 or higher**
- npm (comes bundled with Node.js)

> It is recommended to install Node.js using **NVM**.

---

## Verify Node.js and npm Installation

```bash
node -v
npm -v
```

Node.js version must be 18 or higher.

## Install Angular CLI (Global)
```bash
npm install -g @angular/cli@18
``` 
This installs the latest stable Angular CLI 18.x version.

## Verify Angular CLI Installation
```bash
ng version
```

## Create a New Angular Application (Optional)
```bash
ng new my-angular-app
cd my-angular-app
ng serve
``` 

## Access the application at:

http://localhost:4200

## Upgrade Angular CLI (Future)
```bash
npm uninstall -g @angular/cli
npm install -g @angular/cli@latest
```

## Uninstall Angular CLI (Optional)
```bash
npm uninstall -g @angular/cli
```

Notes

1. Angular CLI depends on Node.js and npm
2. Global installation is recommended for multiple projects
3. Compatible with Angular Material and Nx
4. Works on Linux, macOS, and WSL