# Checking and Modifying Git Config:

To check your Git configuration:

#### 1. Global Configuration:

To see your global configuration (user name, email, etc.), run:

```bash
git config --global --list
```

#### 2. Local Configuration (Inside a Git Repository):
To check the configuration specific to a local repository, navigate to the repository directory and run:

```bash
git config --local --list
```

#### 3. To modify Git configuration:

###### #Setting Global Configuration:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

###### #Setting Local Configuration (Inside a Git Repository):

```bash
git config --local user.name "Your Name"
git config --local user.email "your.email@example.com"
```

Setting Configuration for a Specific Repository:
If you want to set configuration for a specific repository, navigate to that repository and omit --global or --local. This will affect only that repository.