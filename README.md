# WordPress Transient API
This library provides developers to manage all their Transients with version management. 


## Installation
The preferred way to install this extension is through [Composer](http://getcomposer.org/download/).

To install **WP_Transient_API library**, simply:

    $ composer require Varunsridharan/WP_Transient_API

The previous command will only install the necessary files, if you prefer to **download the entire source code** you can use:

    $ composer require Varunsridharan/WP_Transient_API --prefer-source

You can also **clone the complete repository** with Git:

    $ git clone https://github.com/varunsridharan/wp-transient-api.git

Or **install it manually**:

[Download WP_Transient_API.php](https://raw.githubusercontent.com/varunsridharan/wp-transient-api/master/class-transient-wp-api.php):

    $ wget https://raw.githubusercontent.com/varunsridharan/wp-transient-api/master/class-transient-wp-api.php


## Options
| Option | Notes |
| ------ | ----- |
| ***WP Options API*** ||
| `option_prefix` | Custom text to auto prefix for each option added via this class |
| `option_surfix` | Custom text to auto append for each option added via this class | 
| `option_version` | On Which version the given option to be saved
| `option_auto_delete` | if set to true then it auto deletes if the version dose not match|
| ***WP Transient API*** ||
| `transient_prefix` | Custom text to auto prefix for each option added via this class |
| `transient_surfix` | Custom text to auto append for each option added via this class | 
| `transient_version` | On Which version the given option to be saved
| `transient_auto_delete` | if set to true then it auto deletes if the version dose not match|


## Usage 

```php
class YourPlugin_Transient_Api extends Varunsridharan\WordPress\Transient_API {
    protected static $_instance             = NULL;
    
    protected        $is_option             = FALSE;
    protected        $option_prefix         = '';
    protected        $option_surfix         = '';
    protected        $option_version        = 1.0;
    
    protected        $transient_prefix      = '';
    protected        $transient_surfix      = '';
    protected        $transient_version     = 1.0;
    
    protected        $option_auto_delete    = FALSE;
    protected        $transient_auto_delete = FALSE;

    public static function instance() {
        if( self::$_instance === NULL ) {
            self::$_instance = new self;
        }
        return self::$_instance;
    }
}

YourPlugin_Transient_Api::instance();

```

## Global Based On Class Settings 
**Note** : `update only works for if class set to wp options api` 
```php
YourPlugin_Transient_Api::instance()->set('your-key','your-value');
YourPlugin_Transient_Api::instance()->get('your-key'); # Returns the values only if option version matched with $option_version
YourPlugin_Transient_Api::instance()->update('your-key','your-value'); # Updates the options value
YourPlugin_Transient_Api::instance()->delete('your-key'); # Deletes the options and its releated options 
```



## WP Options API With Version Management
```php
YourPlugin_Transient_Api::instance()->add_option('your-key','your-value');
YourPlugin_Transient_Api::instance()->get_option('your-key'); # Returns the values only if option version matched with $option_version
YourPlugin_Transient_Api::instance()->update_option('your-key','your-value'); # Updates the options value
YourPlugin_Transient_Api::instance()->delete_option('your-key'); # Deletes the options and its releated options 
```


## WP Transient API With Version Management
```php
YourPlugin_Transient_Api::instance()->add_transient('your-key','your-value',2000);
YourPlugin_Transient_Api::instance()->get_transient('your-key'); # Returns the values only if option version matched with $transient_version
YourPlugin_Transient_Api::instance()->delete_transient('your-key'); # Deletes the options and its releated options 
```


---
## Sponsored By
[![DigitalOcean](https://vsp.ams3.cdn.digitaloceanspaces.com/cdn/DO_Logo_Horizontal_Blue.png)](https://s.svarun.in/Ef)
