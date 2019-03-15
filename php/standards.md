## Standards

These standards are extensions of [PSR-2](https://www.php-fig.org/psr/psr-2).

## TL;DR

- [Arrays](#arrays)
- [Comments](#comments)
- [Strings](#strings)
- [Variables](#variables)

<a name="arrays"></a>

### Arrays

- Use `[]` instead of `array()` for array definitions.
- Use multiple lines for an very long array because of readable reason.
- Use a trailing comma after the last item of a multiple-line array.

```php
// Bad
$numbers = array(1, 2, 3);

$sentences = ['This is the first sentence.', 'This is the second sentence.', 'This is the third sentence.'];

$words = ['one', 'two', 'three',];
$words = [
    'one',
    'two',
    'three' // missing the trailling comma
];
```

```php
// Good
$numbers = [1, 2, 3];

$sentences = [
    'This is the first sentence.',
    'This is the second sentence.',
    'This is the third sentence.',
];

$words = ['one', 'two', 'three'];
$words = $words = [
    'one',
    'two',
    'three',
];
```

<a name="comments"></a>

### Comments

- TODO

<a name="strings"></a>

### Strings

- Only use double quotes `"` for a string that contains variables.

```php
// Bad
$message = "This string does not contain varirables.";

// Good
$message = 'This string does not contain variables.';
$message = "Hello, {$name}";
```

<a name="variables"></a>

### Variables

- Do not declare a variable starts with `_` character.
- Do not use `snakeCase` syntax to declare a variable. Use `camelCase` syntax instead.

```php
// Bad
$_surname = 'Nguyen';
$first_name = 'Quynh';

// Good
$surname = 'Nguyen';
$firstName = 'Quynh';
```
