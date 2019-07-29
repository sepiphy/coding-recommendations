These recommendations inherit [PSR-1](https://www.php-fig.org/psr/psr-1) and [PSR-2](https://www.php-fig.org/psr/psr-2).

## TL;DR

- [Common](#common)
- [Arrays](#arrays)
- [Comments](#comments)
- [Imports](#imports)
- [Strings](#strings)
- [Variables](#variables)
- [Visibility](#visibility)

## Common

- Files **MUST** use only `<?php` the long tags.
- Files **MUST** enable strict mode by default `<?php declare(strict_types=1);`.
- Namespaces and classes **MUST** only follow the [PSR-4](https://www.php-fig.org/psr/psr-4) autoloading standard.
- Constructors **MUST** be always called with parentheses.

<a name="arrays"></a>

### Arrays

- Arrays **MUST** be declared with `[]` instead of `array()`.
- Very long arrays **MUST** be splitted into multiple lines.
- Multi-line arrays **MUST** have a trailling comma after the last item.

```php
// Bad
$numbers = array(1, 2, 3);

$items = ['This is the first item.', 'This is the second item.', 'This is the third item.'];

$words = ['one', 'two', 'three',]; // no trailling comma for the one-line arrays.

$words = [
    'one',
    'two',
    'three' // missing the trailling comma
];
```

```php
// Good
$numbers = [1, 2, 3];

$items = [
    'This is the first item.',
    'This is the second item.',
    'This is the third item.',
];

$words = ['one', 'two', 'three'];

$words = [
    'one',
    'two',
    'three',
];
```

<a name="comments"></a>

### Comments

- Functions or methods docblock **MUST** be declared with these formats.
  - `@param <datatype> $varname`.
  - `@return <datatype>`
  - `@throws <Exception>`

- Classes or interfaces as datatypes **MUST** be short names.

```php

namespace Example;

use Vendor\Subname\FooClass;
use Vendor\Subname\SomeException;

class Example
{
    /**
     * Do something with the object.
     *
     * @param int $first
     * @param string $second
     * @param FooClass $third

     * @return void
     *
     * @throws SomeException
     */
    public function someMethod($first, $second, FooClass $third)
    {
        // Do some stuff.

        throw new SomeException();
    }
}
```

<a name="imports"></a>

### Imports

- Imports **SHOULD** be sorted in the following order: Native (PHP), Library (Third-party), Local (Project).
- Imports of a group **MUST** be sorted by alpha-numeric.

```php
// Bad
namespace Example;

use Symfony\Component\Console\Command;
use Exception;
use Symfony\Component\Console\Application;
use Local\Another\FooClass;
use SplFileInfo;
use Local\Another\BarClass;

// Good
namespace Example;

use Exception;
use SplFileInfo;
use Symfony\Component\Console\Application;
use Symfony\Component\Console\Command;
use Local\Another\BarClass;
use Local\Another\FooClass;
```
<a name="strings"></a>

### Strings

- Double quotes `"` **MUST** be only used for strings containing variables.
- String concatenation statements **MUST NOT** contain white spaces.

```php
// Bad
$message = "This string does not contain varirables.";
$message = 'Hello, ' . $name . '. Welcome to PHP world.';

// Good
$message = 'This string does not contain variables.';
$message = "Hello, {$name}";
$message = 'Hello, '.$name.'. Welcome to PHP world.';
```

<a name="variables"></a>

### Variables

- Variable names **MUST NOT** contain underscore character (`_`).
- Variable names **MUST** be `camelCase` style, not `snake_case`.

```php
// Bad
$first_name = 'Quynh';
$_surname = 'Nguyen';

// Good
$firstName = 'Quynh';
$surname = 'Nguyen';
```

<a name="visibility"></a>

### Visibility

- Class constants **SHOULD** be declared with `const` only, not use `public`, `protected` or `private`.
- Non-public attributes and methods (including static candidates) **SHOULD** be declared with `protected` only, not `private`. Because it's easy to extend in the inheritance members. All modifications **SHOULD** be decided by software developers.
- Constants, properties and methods **SHOULD** be declared in the following order:
  - Constants (public, protected, private)
  - Static properties (public, protected, private)
  - Properties (public, protected, private)
  - Static methods (public, protected, private)
  - Magic methods (public, protected, private)
  - Methods (public, protected, private)

```php
// Bad
class Example
{
    public const LANGUAGE = 'PHP';
    protected const VERSION = '7.1';
    private const INTERPRETER = 'HHVM'

    private static function foo()
    {
        //
    }

    private function bar()
    {
        //
    }
}

// Good
class Example
{
    const LANGUAGE = 'PHP';
    const VERSION = '7.1';
    const INTERPRETER = 'Zend';

    protected static function foo()
    {
        //
    }

    private function bar()
    {
        //
    }
}
```
