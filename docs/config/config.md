config file in `https://cockpit-example/settings/edit`

````yaml
app.name: Content

session.name: cockpit_local

# base url
base_url: https://cockpit-example
site_url: /
# use cockpit url for having resulting paths with domain (e.g. image styles)
# site_url: https://cockpit-example
base_route: /
# thumbs.url: https://cockpit-example/
# assets.url: https://cockpit-example/

# define globally site language, otherwise will get from the user
i18n: en

# define the languages you want to manage
languages:
    en: English

# define additional groups
groups:
    api:
        $admin: false
        cockpit:
            backend: false
            finder: false
        BackupAndRestore:
            manage.create: true
    author:
        $admin: false
        $vars:
            finder.path: /upload
            finder.allowed_uploads: pdf, png, jpg
            assets.allowed_uploads: png, jpg
        BackupAndRestore:
            manage.view: true
            manage.download: true
        cockpit:
            backend: true
            finder: true
        imagestyles:
            manage.view: true
            manage.admin: false

# Cors settings
cors:
  allowedHeaders: 'X-Requested-With, Content-Type, Origin, Cache-Control, Pragma, Authorization, Accept, Accept-Encoding'
  allowedMethods: 'PUT, POST, GET, OPTIONS, DELETE'
  allowedOrigins: 'http://site.com'
  maxAge: 500
  allowCredentials: true
  exposedHeaders: true
````