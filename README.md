# scripts.sh

A collection of scripts I use repeatedly.

## Installation

1. Clone repository
    ```shell
    git clone git@github.com:dannyvankooten/scripts.sh.git ~/Scripts
    ```
2. Add folder to your `$PATH` variable, so commands can be used globally
    ```shell
    echo '# scripts.sh (https://github.com/dannyvankooten/scripts.sh)' >> ~/.bash_profile
    echo 'export PATH="~/Scripts:$PATH"' >> ~/.bash_profile
    ```
3. Make sure all scripts are executable
    ```shell
    chmod +x ~/Scripts/*
    ```
4. Enjoy!

## Usage

#### Prepare WordPress plugin package

This takes a Git repository, builds all assets, languages & an optimized autoloader, changes the version to the specified version and then creates a stripped-down .zip package for distribution.

```shell
# wp-package $PLUGIN_DIRECTORY $VERSION $DESTINATION
wp-package . 1.0 ~/releases
```

#### Release WordPress plugin to .org SVN

This will automatically extract the plugin name and version number from the given package.

```shell
# wp-release-org $PACKAGE
wp-release-org ~/releases/mailchimp-for-wp-3.0.zip
```

#### Bump version

This bumps the version number in the main plugin file, `readme.txt` and `*.json`.

```shell
# wp-bump-version $VERSION
wp-bump-version 1.0.1
```

#### Run default Gulp/Grunt tasks

Installs NPM deps (if needed) and runs Gulp or Grunt.

```shell
dvk-build assets
```

#### Update language files

Pulls updated language files from Transifex and creates `.mo` files out of it.

```shell
dvk-build languages
```

#### Create optimized autoloader

Removes all developer dependencies and creates an optimized autoloader.

```shell
dvk-build autoloader
```

#### Copy `CHANGELOG.md` to `readme.txt` changelog section.

```shell
wp-update-changelog
```