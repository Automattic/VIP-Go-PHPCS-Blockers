# VIP Go PHPCS Standard for Blockers

This is a ruleset for PHPCS intended to show all known VIP Go incompatible code as errors. This doesn't define any sniffs but references them from other coding standards.

Some useful defaults are set but can be overridden using `phpcs` flags:

* PHP memory_limit set to 1024M
* Show sniff codes in the report
* Only scan files with a php extension

# Installing

## Overview

* Install [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer) and the [WordPress Coding Standards](https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards)
* Add the PHPCS binaries to your `PATH`
* Install this standard
* Add both the WordPress Coding Standards and this standards to PHPCS

## Example

We'll install the above from source to the `~/projects` directory. Feel free to change this to the directory of your choice and replace accordingly in the commands below.

### Install PHPCS and the WordPress Coding Standards

```
cd ~/projects
git clone https://github.com/squizlabs/PHP_CodeSniffer.git phpcs
git clone -b master https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards.git wpcs
```

### Add PHPCS binaries to your `PATH`

```
echo 'export PATH="~/projects/phpcs/bin:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
```
If you are using a different shell, adjust the above to use your profile or rc file.

## Install this standard

```
git clone https://github.com/Automattic/VIP-Go-PHPCS-Blockers
```

### Add both coding standards to PHPCS

```
cd phpcs
phpcs --config-set installed_paths ../wpcs,../VIP-Go-PHPCS-Blockers
```

# Usage

To use this standard, pass in `--standard=VIP-Go-PHPCS-Blockers` to your `phpcs` command. 

For example, to scan the PHP code in the current directory using this standard:
```
phpcs --standard=VIP-Go-PHPCS-Blockers .
```

