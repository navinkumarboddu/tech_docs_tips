### To install the latest stable versions of Docker CLI, Docker Engine, and their dependencies:

###### 1. Download the script
 ```bash   
        curl -fsSL https://get.docker.com -o install-docker.sh
 ```

######  2. verify the script's content
 ```bash 
        cat install-docker.sh
```

######  3. run the script with --dry-run to verify the steps it executes
 ```bash
        sh install-docker.sh --dry-run
```

######  4. run the script either as root, or using sudo to perform the installation.
 ```bash 
        sudo sh install-docker.sh
```

######  5. Verify the Docker installation
 ```bash 
         docker --version
```