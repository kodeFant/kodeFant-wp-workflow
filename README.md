# kodeFant WordPress WorkFlow

Needs to already be installed on system:

- Laravel Valet
- gitignore.io
- Visual Studio Code

## 1. Install WordPress

```
curl -O https://wordpress.org/latest.zip
unzip latest.zip
mv wordpress [project-name]
rm latest.zip
```

- Create a new database in Sequel Pro
- Do the Wordpress setup via project-name .test URL

Then cd into your WordPress Folder in terminal

```
cd [project-name]
```

## 2. Initialize git

```
gi wordpress >> .gitignore
git init
git add .
git commit -m "First Commit"
```

- Create new [Github](https://github.com/new) or [BitBucket](https://bitbucket.org/repo/create) repository
- Follow instruction to connect to local git repository

## 3. Add Starter Wordpress Theme
