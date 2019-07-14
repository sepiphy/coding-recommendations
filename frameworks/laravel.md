These recommendations inherit [PHP rules](../languages/php.md).

### TL;DR

- [Comments](#comments)

<a name="comments"></a>

### Comments

- Functions or methods docblock **MUST** be declared with these formats.
  - `@param  <datatype>  $varname`.
  - `@return <datatype>`
  - `@throws <Exception>`

- Classes or interfaces as datatypes **MUST** be full names.

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
     * @param \Vendor\Subname\SomeClass $third
     * @return void
     *
     * @throws \Vendor\Subname\SomeException
     */
    public function someMethod($first, $second, SomeClass $third)
    {
        // Do some stuff.

        throw new SomeException();
    }
}
```
