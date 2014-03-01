# Demo - une extension en 5min

## Hello

```shell
zephir help

zephir init hello

cd hello

tree ./

more config.json

touch hello/hello.zep
```

```zep
namespace Hello;

class Hello
{
    public function __construct(string name, int iterations)
    {
        while iterations > 0 {
            let iterations -= 1;
            echo sprintf("Hello %s!\n", name);
        }
    }
}
```

```shell
zephir build

    Preparing for PHP compilation...
    Preparing configuration file...
    Compiling...
    Installing...
    [sudo] password for dalexandre:
    Extension installed!
    Add extension=hello.so to your php.ini
    Don't forget to restart your web server

php -dextension=hello.so --ri hello                                                                                                                                                                                        23:59:12

    hello => enabled
    Author =>
    Version => 0.0.1
    Powered by Zephir => Version 0.3.10a

php -dextension=hello.so -a

<?php
new Hello\Hello("BeZend", 1);
