Speaker: Ryan Weaver -- @weaverryan https://twitter.com/weaverryan

Slides: http://www.slideshare.net/weaverryan/the-wonderful-world-of-symfony-components

# Wonderful World of Symfony Components and Composer

### Sidebar
- Symfony is made up of 23 components
- Available in composer

## Life Before Components
- Hard to share between projects
- Hard to autoload files
- Dependencies?
- How to store files in project?

Issues:
- PHP is fragmented

### Fragmentation
- More information we have to know
- Difficult to hire
- Disjointed forums, Stack Overflow
- No interoperability

#### Components are shared across all of PHP

- Act 1
  - Make Sharing Sexy
    - PHP-FIG (United Nations of PHP)
    - The problem of Autoloading
      - SF1 autoloader doesn't know where the ZF1 classes are
      - every framework has its own autoloader
    - PSR-0 Class Naming Conventions
  	- Managing Vendors
  	  - Composer
  	    - Add composer.json
  	    - Run composer.phar (install)
  	    - Composer also provides an autoloader
- Act 2
  - Your friendly, neighborhood SF components
    - Just refer to the slide. SRSLY.
      - HttpFoundation
        - symfony/http-foundation
      - HttpKernel
        - symfony/http-kernel
      - EventDispatcher
        - symfony/event-dispatcher
      - Routing
        - symfony/routing
    - Level 5
      - Framework
    - Additional libraries
      - Process
        - symfony/process
      - Finder
        - symfony/finder
      - Filesystem
        - symfony/filesystem
      - Console
        - symfony/console
      - DomCrawler
        - symfony/domcrawler
      - CssCrawler
        - symfony/csscrawler
      - Config
        - symfony/config
      - Validator
        - symfony/validator

How do we find libraries?
- Packagist
- Github
