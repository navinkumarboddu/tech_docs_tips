# Install Miniconda on Ubuntu

To install Miniconda on Ubuntu, follow these steps:

#### 1. Download the Miniconda Installer

First, download the latest Miniconda installer for Linux. You can choose either the Python 3 or Python 2 version. Here's how to download the Python 3 version:
```markdown
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
```
Note: repo link can be old, so use latest link for Miniconda

#### 2. Verify the Installer (Optional)

To ensure the integrity of the downloaded installer, you can verify its SHA-256 checksum:
```markdown
sha256sum miniconda.sh
```

Compare the output with the checksum provided on the Miniconda download page.

#### 3. Run the Installer

Run the installer script:
```markdown
bash miniconda.sh
```

You'll be prompted to accept the license agreement and choose the installation directory. The default is typically ~/miniconda3.

#### 4. Initialize Conda

After installation, you'll need to initialize Conda:
```markdown
~/miniconda3/bin/conda init
```

This will modify your shell's startup file (e.g., .bashrc or .zshrc) to include Conda.

#### 5. Activate the Installation

Restart your terminal or run the following command to activate the Miniconda installation:
```markdown
source ~/.bashrc
```

6. Verify the Installation

Finally, verify that Conda is installed and working:
```markdown
conda --version
```

You should see the version number of Conda.

#### 7. (Optional) Create a New Conda Environment

To create a new Conda environment with a specific version of Python, you can use:
```markdown
conda create --name myenv python=3.9
```

Activate the environment with:
```markdown
conda activate myenv
```

You now have Miniconda installed on your Ubuntu system!