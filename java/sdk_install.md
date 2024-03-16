The installation guide for SDKMan can be found at: [Installation - SDKMAN! the Software Development Kit Manager](https://sdkman.io/install).

##### Installing SDKMAN! on UNIX is a breeze. 

It effortlessly sets up on macOS, Linux and Windows (with WSL). Plus, it's compatible with both Bash and ZSH shells.

###### #Just launch a new terminal and type in:

```bash
$ curl -s "https://get.sdkman.io" | bash
```

###### #Follow the on-screen instructions to wrap up the installation. Afterward, open a new terminal or run the following in the same shell:

```bash
$ source "$HOME/.sdkman/bin/sdkman-init.sh"
```

###### #Lastly, run the following snippet to confirm the installation's success:

```bash
$ sdk version
```

###### # You should see output containing the latest script and native versions:

```bash
SDKMAN!
script: 5.18.2
native: 0.4.6
```