# Composer Gavel

[![Gavel](img/noun_131778_cc.png)](https://thenounproject.com/search/?q=gavel&i=131778)

_I judge your Composer to be insufficent_

[![CircleCI](https://circleci.com/gh/deviantintegral/composer-gavel.svg?style=svg)](https://circleci.com/gh/deviantintegral/composer-gavel) [![Maintainability](https://api.codeclimate.com/v1/badges/d5b9443b2d5daf11d34a/maintainability)](https://codeclimate.com/github/deviantintegral/composer-gavel/maintainability) [![Test Coverage](https://api.codeclimate.com/v1/badges/d5b9443b2d5daf11d34a/test_coverage)](https://codeclimate.com/github/deviantintegral/composer-gavel/test_coverage) [![Packagist](https://img.shields.io/packagist/dt/deviantintegral/composer-gavel.svg)](https://packagist.org/packages/deviantintegral/composer-gavel)

## Rationale

We've worked on many projects with larger teams where developers end up with
multiple versions of composer all over their local environments. This plugin
will ensure that composer version warnings can't be ignored by developers, which
is especially useful when developers need to run `composer update`.

## Usage

`$ composer global require deviantintegral/composer-gavel`

### Add plugin to your project and update other dependencies

1. `$ composer require --dev deviantintegral/composer-gavel`
1. `$ composer update`

### Add without updating anything

1. `$ composer require --dev deviantintegral/composer-gavel`
1. Update the composer.lock hash with `$ composer update --lock`.

When the running composer version does not satisfy the constraint, an error
will be thrown.

![gavel error](img/gavel-error.png)

It's recommended to require this plugin on a per-project basis as well as
globally. If the plugin is not globally installed, then the version check will
not run during the very first composer install or update. The per-project
requirement ensures that the plugin is activated after the initial install.
The composer version is a root-only key and is not used in dependencies.
