# kodeFant WordPress WorkFlow

Already installed on system:
Laravel Valet to automatically set up

## 1. Install WordPress

```
curl -O https://wordpress.org/latest.zip
unzip latest.zip
mv wordpress [project-name]
rm latest.zip
```

- Create a new database in Sequel Pro
- Do the Wordpress setup via project-name.test
- cd into your WordPress Theme Folder
- Initialize git

```
cd [project-name]
```

## 2. Initialise git

```
touch .gitignore
nano .gitignore
```

Paste this into .gitignore:

```
# Created by https://www.gitignore.io/api/wordpress

### WordPress ###
*.log
wp-config.php
wp-content/advanced-cache.php
wp-content/backup-db/
wp-content/backups/
wp-content/blogs.dir/
wp-content/cache/
wp-content/upgrade/
wp-content/uploads/
wp-content/mu-plugins/
wp-content/wp-cache-config.php
wp-content/plugins/hello.php

/.htaccess
/license.txt
/readme.html
/sitemap.xml
/sitemap.xml.gz



# End of https://www.gitignore.io/api/wordpress
```
