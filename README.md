# kodeFant WordPress WorkFlow (FTP)

Needs to already be installed on system:

- Laravel Valet (I don't have enough RAM for Vagrant)
- gitignore.io
- Visual Studio Code
- git-ftp
- yarn

todos:
[ ] make complete sh-script with [project-name] and [theme-name] as variables

## 1. Install WordPress

First, create a MySQL database:

```
mysql -u root -e "create database [project-name]";
```

Alternative 1: Vanilla WordPress:

```
curl -O https://wordpress.org/latest.zip
unzip latest.zip
mv wordpress [project-name]
rm latest.zip
cd [project-name]
gi wordpress >> .gitignore
```

- Do the Wordpress setup via project-name .test URL

Alternative 2: Bedrock WordPress Boilerplate:

```
composer create-project roots/bedrock [project-name]
cd [project-name]
code .env
```

In **.env**, edit the following:
**DB_NAME** - [project-name]
**DB_USER** - Database user
**DB_PASSWORD** - Database password
**WP_ENV** - development
**WP_HOME** - Full URL to WordPress home (http://example.com)
**WP_SITEURL** - Full URL to WordPress including subdirectory (http://example.com/wp)
AUTH_KEY, SECURE_AUTH_KEY, LOGGED_IN_KEY, NONCE_KEY, AUTH_SALT, SECURE_AUTH_SALT, LOGGED_IN_SALT, NONCE_SALT - Generate with [WordPress Salt Generator](https://cdn.roots.io/salts.html)

## 2. Initialize git

```
git init
git add .
git commit -m "First Commit"
```

- Create new [Github](https://github.com/new) or [BitBucket](https://bitbucket.org/repo/create) repository
- Follow instruction to connect to local git repository

## 3. Add Starter Wordpress Theme

cd to theme folder

Alternative 1: Vanilla WordPress:

```
cd wp-content/themes
```

Alternative 2: Bedrock WordPress Boilerplate:

```
cd web/app/themes
composer create-project roots/sage [theme-name]
cd [theme-name]
yarn
```

## 4. Deploy with git-ftp

### Setup

```
git config git-ftp.url "ftp://ftp.example.net:21/public_html"
git config git-ftp.user "ftp-user"
git config git-ftp.password "secr3t"
```

### Upload all files

```
git ftp init
```

### Or if the files are already there

```
git ftp catchup
```

### Work and deploy

```
echo "new content" >> index.txt
git commit index.txt -m "Add new content"
git ftp push
```

```

```
