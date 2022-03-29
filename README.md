# Configure Local Environment

```bash
# Confirm Python 3 is installed
$ python3 --version

## output:
Python 3.8.10

# Install venv
$ sudo apt install python3.8-venv

# Install pip
$ sudo apt install python3-pip

# Clone this repo

# Create venv (virtual environment)
$ python3 -m venv venv

# Activate venv
$ source venv/bin/activate

# Run locally
$ python3 hello_world_package_jaylaw/hello_world_module.py

## output:
hello python

```

# Publish

```bash
# Create 'distribution package'
$ python3 -m build

# Creates the following:
# file - hello_world_package_jaylaw.egg-info
# dir - dist/

# Install twine if it's not already installed
$ python3 -m pip install --upgrade twine

# Upload archives
$ python3 -m twine upload --repository testpypi dist/*

# username:  __token__
# password:  [API TOKEN]

# Navigate to the url to confirm upload 
# https://test.pypi.org/project/hello-world-package-jaylaw/
```

# Test Published Package

```bash
# In a seperate directory.  Create dir to test
$ mkdir python_test
$ cd python_test

# Create venv
$ python3 -m venv venv

# Activate venv
$ source venv/bin/activate

# Install package
$ python3 -m pip install --index-url https://test.pypi.org/simple/ --no-deps hello_world_package_jaylaw

# Create main.py
$ echo "from hello_world_package_jaylaw import hello_world_module" >> main.py
$ echo "hello_world_module.main()" >> main.py

# Execute the app
$ python3 main.py

## output
hello python

```

# Tagging

```bash
# add tag
$ git tag -a 1.0.3 -m 'Version 1.0.3'

# remove tag
$ git tag -d 1.0.2


```