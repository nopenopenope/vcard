# VCard PHP library

[![Latest Stable Version](http://img.shields.io/packagist/v/seec/vcard.svg)](https://packagist.org/packages/seec/vcard)
[![License](http://img.shields.io/badge/license-MIT-lightgrey.svg)](https://github.com/jeroendesloovere/vcard/blob/master/LICENSE)
[![Test Pipeline](https://github.com/nopenopenope/vcard/actions/workflows/ci.yaml/badge.svg)](https://github.com/nopenopenope/vcard/actions/workflows/ci.yaml)

This VCard PHP library can generate a vCard with some data. When using an iOS device < iOS 8 it will export as a .ics
file because iOS devices don't support the default .vcf files.

## Usage

### Installation

```bash
composer require seec/vcard
```

This will install the latest version of vcard with [Composer](https://getcomposer.org)

### Example

> [View all examples](/examples/example.php) or check [the VCard class](/src_/VCard.php).

### Parsing examples

The parser can either get passed a VCard string, like so:

```php
// load VCardParser classes
use SEEC\VCard\VCardParser;

$parser = new VCardParser($vcardString);
echo $parser->getCardAtIndex(0)->fullname; // Prints the full name.
```

Or by using a factory method with a file name:

```php
$parser = VCardParser::parseFromFile('path/to/file.vcf');
echo $parser->getCardAtIndex(0)->getName(); // Prints the full name.
```

> [View the parsing example](/examples/example_parsing.php) or check the [the VCardParser class](/src_/VCardParser.php)
> class.

## Documentation

The goal is to use no comments at all in the code. Since this is a fork, some things might not be as straight forward as
one could wish for. Feel free to refactor old stuff and add it via a new PR!

More info on how to work with GitHub on help.github.com.

### Development

In order to run the development instance of this repository, you can very easily utilize the shipped docker-compose
package.

```bash 
docker compose up --build
```

Afterwards you will have an instance with PHP8.2q running that you can use to develop your changes. Xdebug is enabled by
default, so you can use your IDE to debug the code.

## Credits

- [Jeroen Desloovere](https://github.com/jeroendesloovere)
- [Maximilian Graf Schimmelmann](https://www.schimmelmann.org)
- [All Contributors](https://github.com/jeroendesloovere/vcard/contributors)

## License

The module is licensed under [MIT](./LICENSE.md). In short, this license allows you to do everything as long as the
copyright statement stays present.
