To install Python 2 (python) and Python 3 (python3) on Ubuntu, follow these steps:
1. Update the Package List

First, ensure your package list is up-to-date:

sudo apt update

2. Install Python 2

Python 2 has reached end-of-life, but you can still install it if you need it:

sudo apt install python2 -y

To verify the installation:

python2 --version

3. Install Python 3

Python 3 is the default Python version on modern Ubuntu systems. To install Python 3:

sudo apt install python3 -y

To verify the installation:

python3 --version

4. Install python-is-python3 (Optional)

If you want the python command to point to Python 3 instead of Python 2 (since Python 2 is deprecated), you can install the python-is-python3 package:

sudo apt install python-is-python3 -y

5. Install pip for Both Versions

To install pip (the Python package manager) for both Python 2 and Python 3:

    For Python 2:

sudo apt install python2-pip -y

For Python 3:

    sudo apt install python3-pip -y

6. Verify the Installations

Check that both Python versions and pip are installed correctly:

    Python 2:

python2 --version
pip2 --version

Python 3:

    python3 --version
    pip3 --version

You now have both Python 2 and Python 3 installed on your Ubuntu system.