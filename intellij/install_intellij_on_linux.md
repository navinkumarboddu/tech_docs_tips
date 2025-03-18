# 🚀 Install IntelliJ IDEA Community Edition on Linux  

This guide covers how to **download, install, and configure IntelliJ IDEA** on Linux, enabling it to launch with the `idea` or `.idea` command.

---

## 📌 Installation Steps

### 1️⃣ Download IntelliJ IDEA  
Visit the official [JetBrains IntelliJ IDEA Download page](https://www.jetbrains.com/idea/download) and download the **Linux (.tar.gz)** version.

Alternatively, use `wget`:
```bash
wget https://download.jetbrains.com/idea/ideaIC-latest.tar.gz -O ideaIC.tar.gz
```

---

### 2️⃣ Extract and Install
Extract the downloaded file and move it to `/opt/`:
```bash
tar -xzf ideaIC.tar.gz
sudo mv idea-IC-* /opt/intellij-idea
```

---

### 3️⃣ Create a Symlink for Easy Access  
Run the following command to create a system-wide shortcut:
```bash
sudo ln -s /opt/intellij-idea/bin/idea.sh /usr/local/bin/idea
```
Now, you can start IntelliJ IDEA by simply running:
```bash
idea
```

---

### 4️⃣ (Optional) Create a Desktop Entry  
To add IntelliJ IDEA to your application menu, create a `.desktop` file:
```bash
echo "[Desktop Entry]
Name=IntelliJ IDEA Community
Exec=/opt/intellij-idea/bin/idea.sh
Icon=/opt/intellij-idea/bin/idea.png
Type=Application
Categories=Development;" | sudo tee /usr/share/applications/intellij-idea.desktop
```

---

### 5️⃣ Enable `.idea` Shortcut (Optional)
If you want to open projects using `.idea` command inside project directories:

1. Create an alias:
   ```bash
   echo 'alias .idea="idea $(pwd)"' >> ~/.bashrc
   source ~/.bashrc
   ```
2. Now, in any IntelliJ project folder, run:
   ```bash
   .idea
   ```
   and it will open IntelliJ with the current directory as a project.

---

## ✅ Running IntelliJ IDEA
- Open from terminal using:
  ```bash
  idea
  ```
- Open a project inside a directory:
  ```bash
  cd /path/to/project
  .idea
  ```
- Open from the application menu (if the desktop entry was created).

---

## 🛠️ Uninstall IntelliJ IDEA
To remove IntelliJ IDEA from your system:
```bash
sudo rm -rf /opt/intellij-idea
sudo rm /usr/local/bin/idea
sudo rm /usr/share/applications/intellij-idea.desktop
```

---

## 🎉 Enjoy IntelliJ IDEA on Linux! Happy Coding! 🚀
