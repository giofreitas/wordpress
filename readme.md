# giofreitas/wordpress
This metapackage sets up everything you need to get WordPress running successfully with composer.

[giofreitas/wordpress-composer-setup](https://github.com/giofreitas/wordpress-composer-setup) will create the __wp-config.php__ file with the necessary definitions to let WordPress to be suitable with composer. The __wp-config.php__ is the only non-core file that surely, will be loaded either in frontend or in admin, so its a good place to setup everything we need.

##### Usage
To Setup a WordPress installation including wp-config.php, add the following to your package's composer file:

```
"require": {
    "giofreitas/wordpress": "4.9.5"
}
```

You can manually set the site url in extra (do not define if you want it to be dynamic through all environments):

```
"extra": {
    "wordpress-site-url": "localhost"
}
```

We can also make use of some options from [johnpbloch/wordpress-core-installer](https://github.com/johnpbloch/wordpress-core-installer) and [composer/installers](https://github.com/composer/installers) to change some default configurations:

```
"extra": {
    "wordpress-install-dir": "wordpress"
    "installer-paths": {
        "wp-content/themes/{$name}/": ["type:wordpress-theme"],
        "wp-content/plugins/{$name}/": ["type:wordpress-plugin"]
        "wp-content/mu-plugins/{$name}/": ["type:wordpress-muplugin"]
    }
}
```