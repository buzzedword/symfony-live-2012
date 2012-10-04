Speaker: Jordi Boggiano -- @seldaek https://twitter.com/seldaek

Slides: http://slides.seld.be/?file=2012-09-28+In-Depth+with+Composer.html#1

# In-Depth with Composer

## Use cases

### Installing and updating
- Install/Update work on project deps
- composer installs or updates individual packages

### Install
- Last known state

### Update
- Newest version, updates lock file.

## Using a forked project
- Additional repos take priority over the default ones
- Do not change the package name
  - forks intelligently adopt current package name
  - your branches are available after you add repo config
- "branch name as x.x.x"
  - uses version specification as version dependency.

## Private packages with Satis
- use satis.json vs composer.json to hide repositories.
- Satis also allows for proxying

## Renaming packages safely
``` json
{
	"name" : "new/name",
	"replace":{
		"old/name" : "*"
	}
}
```

### Composer Execution Order

1. Bootstrap
  - Loading of the root package
  - First install or Update
    - Create install requests for the requirements
    - on update: force update installed dev packages to latest
  - install from lock file
    - load lock file as a repository
    - create install requests for all its packages
2. Creation of the package pool
  - Platform repository
    - `composer show --platform`
  - Local installed repositories
    - `composer show --installed`
  - Locked respository (install only)
  - Custom repositories (project)
  - Custom repositories (user level config)
  - Packagist
3. Dependency Resolution
  - Solver + Request + Pool
  - Shake until you get a list of operations
4. Install/Update/Uninstall
  - --prefer-source forces source install (git clone)
  - --prefer-dist forces dist install (zip download)
  - --dry-run if you are just curious
  - --verbose / -v to see more details
  5. Wrap-up
    - Writing lock file (update or first install only)
      - `composer install`
    - Generating autoloader
      - `composer dump-autoload --optimize`
    - post-install-cmd / post-update-cmd scripts fire
      - don't need scripts?
        ``` bash
        $ composer install --no-scripts
        # default symfony app/console
        ```

### Package not auto-updating?

Validate your config
``` bash
$ composer validate
./composer.json is valid
```

### Strange behavior

- Update composer
  - `composer self-update`
- Check your setup's settings
  - `curl -s https://getcomposer.org/installer | php -- --check`
- Update your deps
  - `composer update -v`
- Reinstall your deps
  ``` bash
  rm -rf vendor/
  composer update -v
  ```
- Report a bug
