# Install VScode on Linux

To install Visual Studio Code on Ubuntu using a .tar.gz file, follow these steps:

#### 1. Download the VS Code .tar.gz File

First, download the latest Visual Studio Code .tar.gz file from the official website or using wget.

#### 2. Extract the Tarball

Extract the downloaded .tar.gz file:
```markdown
tar -xvzf vscode.tar.gz
```

This will create a directory named something like VSCode-linux-x64.

#### 3. Move the Extracted Files to /opt

Move the extracted files to /opt so that it's accessible system-wide:
```markdown
sudo mv VSCode-linux-x64 /opt/vscode
```

#### 4. Create a Symlink

To make VS Code accessible via the code command, create a symbolic link:
```markdown
sudo ln -s /opt/vscode/code /usr/local/bin/code
```

#### 5. (Optional) Create a Desktop Entry

To make Visual Studio Code appear in your applications menu, create a .desktop file:
```markdown
sudo nano /usr/share/applications/vscode.desktop
```

Add the following content:
```markdown
[Desktop Entry]
Version=1.0
Name=Visual Studio Code
Comment=Code Editing. Redefined.
Exec=/opt/vscode/code --no-sandbox %F
Icon=/opt/vscode/resources/app/resources/linux/code.png
Terminal=false
Type=Application
Categories=Development;IDE;
StartupNotify=true
```

Save and close the file.

#### 6. Run Visual Studio Code

You can now run VS Code by typing code in the terminal:
```markdown
code
```

Or by finding it in your applications menu.

#### 7. (Optional) Update VS Code

To update VS Code in the future, download the latest .tar.gz file, extract it, and replace the contents of /opt/vscode with the new files.

You now have Visual Studio Code installed on your Ubuntu system using the .tar.gz file!