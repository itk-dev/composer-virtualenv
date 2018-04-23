Composer virtualenv
===================

A simple virtual environment for `composer`.

Inspired by Python's
[`virtualenv`](https://virtualenv.pypa.io/en/stable/), this package
adds a script for prepending `vendor/bin` to the `PATH` variable to
make it easier to run commands installed via `composer`.

Background
----------

Assume your `composer.json` contains

```json
    "require-dev": {
        "phpunit/phpunit": "^6.5",
        "drush/drush": "^9.2"
    }
```

After running `composer install` you have to make sure to run
`vendor/bin/phpunit` or `vendor/bin/drush`, respectively, to run the
right command. If you just run `phpunit` you'll will run any globally
installed version of `phpunit` (or get an error if `phpunit` is not
installed).

Composer virtualenv, helps you run the right commands, i.e. the ones
installed using `composer`, without having to (remember to) type
`vendor/bin/` every time.

Installation
------------

```sh
composer require itk-dev/composer-virtualenv dev-master
```

Activating the virtual environment
----------------------------------

To deactivate the virtual environment, run

```sh
source vendor/bin/activate
```

**Note**: It is important to `source` the script – it will not work if
it is run.

This prepends the path `vendor/bin` to the `PATH` environment
variable, and any command installed using `composer` will be run
instead of any globally available command of the same name.

Deactivating the virtual environment
------------------------------------

To deactivate the virtual environment and restore the `PATH`
variable to its original value, run

```sh
deactivate
```
