### Template to handling all requests to single file (public/index.php).

1. In `ROOT/.htaccess`, use below template.
```
DirectoryIndex public/index.php

RewriteEngine On
# RewriteBase /[app-path]/

RewriteRule ^$ public/index.php [L]

RewriteCond %{REQUEST_URI} !^public/
RewriteCond %{REQUEST_URI} !^index\.php$
RewriteRule ^(.+)$ public/$1 [L,NC]
```

2. In `ROOT/public/.htaccess`, use [single-file-routing](./single-file-routing.md) template.
