# PHP-TUF PHP_CodeSniffer Standard

The PHP-TUF PHP_CodeSniffer Standard is a [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) coding standard for PHP-TUF packages.

## Installation & usage

The following steps are opinionated for the purpose of standardization across PHP-TUF repos.

1. Add the standard to your project via Composer:

    ```bash
    composer config repositories.0 git https://github.com/php-tuf/phpcodesniffer-standard
    composer require --dev php-tuf/phpcodesniffer-standard
    ```

1. Make PHP CodeSniffer aware of the standard with [`DealerDirect/phpcodesniffer-composer-installer`](https://github.com/DealerDirect/phpcodesniffer-composer-installer):

    ```bash
    composer require --dev dealerdirect/phpcodesniffer-composer-installer
    ```

1. Add scripts to your `composer.json` for convenient execution:

    ```json
    {
        "scripts": {
            "phpcs": "phpcs -s --standard=PhpTuf ./src ./tests",
            "phpcbf": "phpcbf --standard=PhpTuf ./src ./tests"
        },
        "scripts-descriptions": {
            "phpcs": "Checks code for standards compliance.",
            "phpcbf": "Automatically fixes standards violations where possible."
        }
    }
    ```

1. Check code for standards compliance:

    ```bash
    composer phpcs
    ```

    Automatically fix standards violations where possible:

    ```bash
    composer phpcbf
    ```

1. Optionally [configure PHP Code Sniffer integration in PhpStorm](https://www.jetbrains.com/help/phpstorm/using-php-code-sniffer.html) or your IDE or code editor of choice.
