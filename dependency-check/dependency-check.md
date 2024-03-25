# Dependency-Check
The command line tool of OWASP Dependency-Check to analyze external dependencies and generate a report based on the known vulnerabilities detected.

#### Step 1) 
First, download the command-line tool from the official website [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)

#### Step 2) 
After downloading and extract. Goto dependency-check folder, In the bin directory you can find the executable script. dependency-check.bat file is for running the tool on Windows and the dependency-check.sh file is for running on Linux.
Or we can install it using **Homebrew**
```bash
brew install dependency-check
```

This puts an executable dependency-check script in the /bin directory of your homebrew installation.

#### Step 3)
To scan a folder on the system you can run:

###### Windows
```markdown
dependency-check.bat --project "My App Name" --scan "c:\java\application\lib"
```

###### *nix
```markdown
dependency-check.sh --project "My App Name" --scan "/java/application/lib"
```

#### Step 4)
To view the command line arguments, see the arguments page, or you can run:

###### Windows
```bash
dependency-check.bat --help
```

###### *nix
```bash
dependency-check.sh --help
```