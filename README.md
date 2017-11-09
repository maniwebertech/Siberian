# SiberianCMS: SAE Single App Edition

[Public Roadmap](http://board.siberiancms.com/b/7AYdMDEpFcmt3eZtb/siberiancms-public-roadmap)

![welcome](docs/siberiancms.png)

## Documentation

* [User documentation](http://doc.siberiancms.com)
* [Developer documentation](http://developer.siberiancms.com)

## Installation

### Requirements

## Software

* Recommended OS: `Linux`

    * Works on `OSX` with [homebrew](http://brew.sh/), and on `Windows` with [cygwin](https://www.cygwin.com/)
    
* OpenSSL >=1.0.1

    * with TLS v1.2 support

* [Apache](#apache) or [Nginx](#nginx)

* PHP

    * version: >=5.6, <= 7.0
    
    * extensions: `gd`, `pdo_mysql`, `SimpleXML`, `curl`, `dom`, `SQLite3`.
    
    * functions: `exec()`
    
    * parameters: `allow_url_fopen = On`, `memory_limit >= 128M`

* MySQL/MariaDB >=5.5 with InnoDB/XtraDB engine

* Binaries: 

    * required: `zip`, `unzip`

    * optional: `pngquant` or `optipng`, `jpegoptim`

### Configuration

1. First you will need to either checkout the project `git clone https://github.com/Xtraball/SiberianCMS.git`

    or download the [zip archive](https://github.com/Xtraball/Siberian/archive/master.zip) then extract it on your webserver.

2. Run `npm install` then follow the instructions to update your local shell.

3. Run `./sb init` to init your local project.

3. Configure your environment with either [apache](#apache) or [nginx](#nginx)

When you're done with the previous steps, reload your web server.

### Web installer

* Go to `http://yourdomain.tld` then follow the instructions
![welcome](docs/install-sae.gif)


# Developer package & resources.

---

## Developers

### Platforms

If a custom development is needed for a platform, `cd` to the folder, then push to the local platform, the branch is named `siberian`

- Platforms templates used to build/rebuild are installed from this directory, this ensure the platforms are synced & up-to-date everytime.

- Android* `platforms/cdv-siberian-android`
- iOS* `platforms/cdv-siberian-ios`

The other platforms specific to Siberian which are `cdv-siberian-android-previewer`, `cdv-siberian-ios-previewer` & `cdv-siberian-ios-noads` are automatically synced from their respective parents.

- Rebuilding a platform
    1. run `siberian rebuild platformName` where platformName is `android | android-previewer |ios | ios-noads | ios-previewer | browser`

### Plugins

Every plugin used in the project is forked on GitHub, they are added as submodules in the folder `plugins`

A default branch named `siberian` is used to track and lock our modifications.
    
### Modules

Our standalone modules are tracked into the folder `modules` every module has it's own git, and is versioned independantly of the Siberian Editions


# SiberianCMS command-line interface Help

Available commands are: 

|Command|Description|
|---|---|
|alias|Prints bash aliases to help development|
|clearcache, cc|Clear siberian/var/cache|
|clearlog, cl|Clear siberian/var/log|
|cleanlang|Clean-up duplicates & sort languages CSV files|
|db|Check if databases exists, otherwise create them|
|export-db|Export db tables to schema files|
|init|Initializes DB, project, settings.|
|install|Install forks for cordova-lib.|
|icons|Build ionicons font|
||- install: install required dependencies (OSX Only).|
||icons [install]|
|ions|Start ionic serve in background|
|rebuild|Rebuild a platform:|
||- debug: option will show more informations.|
||- copy: copy platform to siberian/var/apps.|
||- no-manifest: don't call the rebuild manifest hook.|
||rebuild <platform> [copy] [debug] [no-manifest]|
|rebuild-all|Rebuild all platforms|
|syncmodule, sm|Resync a module in the Application|
|type|Switch the Application type 'sae|mae|pe' or print the current if blank|
||note: clearcache is called when changing type.|
||- reset: optional, will set is_installed to 0.|
||- empty: optional, clear all the database.|
||type [type] [reset] [empty]|
|test|Test PHP syntax|
|pack|Pack a module into zip, file is located in ./packages/modules/|
||- If using from a module forlders module_name is optional|
||pack <module_name>|
|packall|Pack all referenced modules|
|prepare|Prepare a platform:|
||- debug: option will show more informations.|
||- copy: copy platform to siberian/var/apps.|
||- no-manifest: don't call the rebuild manifest hook.|
||prepare <platform> [copy] [debug] [no-manifest]|
|manifest|Rebuilds app manifest|
|mver|Update all module version to <version> or only the specified one, in database.|
||- module_name is case-insensitive and is searched with LIKE %module_name%|
||- module_name is optional and if empty all modules versions are changed|
||mver <version> [module_name]|
|npm|Hook for npm version.|
||npm <version>|
|prod|Switch the Application mode to 'production'.|
|dev|Switch the Application mode to 'development'.|
|version|Prints the current SiberianCMS version.|
|linkmodule, lm|Symlink a module from ./modules/ to ./siberian/app/local/modules/|
||lm <module>|
|unlinkmodule, ulm|Remove module symlink|
||ulm <module>|
|syncmodule, sm |Sync all sub-modules/platforms/plugins from git|