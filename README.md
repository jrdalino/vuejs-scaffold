# vuejs-scaffold

## Prerequisites
- Working Directory
```
$ cd ~
$ mkdir environment
$ cd ~/environment
```

- Vue CLI
```
$ npm install -g vue-cli
```

- Git
```
$ git --version
$ git config --global user.name "REPLACE_ME_WITH_YOUR_NAME"
$ git config --global user.email REPLACE_ME_WITH_YOUR_EMAIL@example.com
$ git config --global credential.helper '!aws codecommit credential-helper $@'
$ git config --global credential.UseHttpPath true
```

### Step 1.1: Initialize Vue Project
- 
```
$ cd ~/environment/
$ vue init webpack myproject-consumer-web
$ cd myproject-consumer-web
$ npm install
$ npm run dev
```

### Step 1.2: Create Code Commit Repo
```
$ aws codecommit create-repository --repository-name myproject-consumer-web
```

### Step 1.3: Set up .gitignore
```
$ cd ~/environment/myproject-product-restapi
$ vi .gitignore
```
```
# Byte-compiled / optimized / DLL files
__pycache__/
.api/__pycache__/
.api/products/__pycache__/
*.py[cod]
*$py.class

# C extensions
*.so

# Distribution / packaging
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
pip-wheel-metadata/
share/python-wheels/
*.egg-info/
.installed.cfg
*.egg
MANIFEST

# Unit test / coverage reports
htmlcov/
.tox/
.nox/
.coverage
.coverage.*
.cache
nosetests.xml
coverage.xml
*.cover
.hypothesis/
.pytest_cache/

# Flask stuff:
instance/
.webassets-cache

# Virtual environment
venv
*.pyc
```

### Step 1.2 Import Existing Folder to CodeCommit
```
$ cd ~/environment/myproject-consumer-web
$ git init
$ git add .
$ git commit -m "Initial Commit"
$ git remote add origin https://git-codecommit.ap-southeast-1.amazonaws.com/v1/repos/myproject-consumer-web
$ git remote -v
$ git push -u origin master
```
