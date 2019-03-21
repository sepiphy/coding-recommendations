## Laravel Coding Recommendations

### TL;DR

- [Comments](#comments)

<a name="comments"></a>

### Comments

- Use these formats for a function or method comments.
  - `@param  <datatype>  $varname`.
  - `@return <datatype>`
  - `@throws <Exception>`

> Note: Use the full names for all classes, interfaces and traits.

```php

namespace Example;

use Dir\To\ExClass;
use Dir\To\ExException;

class Example
{
    /**
     * Do something with the object.
     *
     * @param  int  $first
     * @param  string  $second
     * @param  \Dir\To\ExClass  $third
     * @return void
     *
     * @throws \Dir\To\ExException
     */
    public function someMethod($first, $second, ExClass $third)
    {
        //
    }
}
```
