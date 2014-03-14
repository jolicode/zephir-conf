# Demo - une extension en 5min

## Hello

    zephir help

    zephir init hello

    cd hello

    tree ./
    ls -lha ./

    more config.json

    touch hello/hello.zep


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


> Petit jeu des différences avec PHP

    zephir build

> Preparing for PHP compilation...
> Preparing configuration file...
> Compiling...
> Installing...
> [sudo] password for dalexandre:
> Extension installed!
> Add extension=hello.so to your php.ini
> Don't forget to restart your web server

    php -dextension=hello.so --ri hello

> hello => enabled
> Author =>
> Version => 0.0.1
> Powered by Zephir => Version 0.3.10a

    php -dextension=hello.so -a

    new Hello\Hello("BeZend", 1);
    new Hello\Hello("BeZend", 88);
    new Hello\Hello(1337, 88);

> Ajouter "!" après "string", montrer qu'on peux faire du typage fort.
> Pas d'autoloading a mettre en place \o/

## Avantages de la compilation

    namespace Hello;

    class Hello
    {
        public function foo() -> boolean
        {
            return true;
        }
    }


    namespace Hello;

    class Hello
    {
        public function foo() -> boolean
        {
            return this->bar();
        }
    }


    namespace Hello;

    class Hello
    {
        public function foo(<\DateTime> date) -> boolean
        {
            return date;
        }
    }

> Fonctionne quand même...
