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
```
$ cd ~/environment/
$ vue init webpack myproject-consumer-web
$ cd myproject-consumer-web
$ npm run dev
```

### Step 1.2: Create Code Commit Repo
```
$ aws codecommit create-repository --repository-name myproject-consumer-web
```

### Step 1.3: Set up .gitignore
- Automatically created by vue init

### Step 1.2 Import Existing Folder to CodeCommit
```
$ cd ~/environment/myproject-consumer-web
$ git init
$ git add .
$ git commit -m "Initial Commit"
$ git remote add origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/myproject-consumer-web

$ git remote -v
$ git push origin master
```
