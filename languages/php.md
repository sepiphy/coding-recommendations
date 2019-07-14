These recommendations inherit [PSR-1](https://www.php-fig.org/psr/psr-1) and [PSR-2](https://www.php-fig.org/psr/psr-2).

## TL;DR

- [Common](#common)
- [Arrays](#arrays)
- [Comments](#comments)
- [Strings](#strings)
- [Variables](#variables)

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

- Function or method docblock **MUST** be declared with these formats.
  - `@param <datatype> $varname`.
  - `@return <datatype>`
  - `@throws <Exception>`

- Classes or interfaces as datatypes **MUST** be short names.

```php

namespace Example;

use Vendor\Subname\SomeClass;
use Vendor\Subname\SomeException;

class Example
{
    /**
     * Do something with the object.
     *
     * @param int $first
     * @param string $second
     * @param SomeClass $third

     * @return void
     *
     * @throws SomeException
     */
    public function someMethod($first, $second, SomeClass $third)
    {
        // Do some stuff.

        throw new SomeException
    }
}
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
