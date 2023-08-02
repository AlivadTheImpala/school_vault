# Syntax
```php
function function_name([],[],...)
{

}
```
A function in PHP has a basic syntax. first you call it by the "function" keyword followed by the name you choose. Remember the name reflects the purpose of the function. Then parentheses which hold one or more parameters typically, although some built-in php functions don't require a parameter.

Curly braces will then hold the statements and a return value if necessary.
> [!note]
> the square brackets are just there to illustrate parameters. they are not needed.

## Reference arguments
Lets say we have this function named fix_names
```php
$names = fix_names("WILLIAM", "henry", "gatES");
  echo $names[0] . " " . $names[1] . " " . $names[2];

  function fix_names($n1, $n2, $n3)
  {
    $n1 = ucfirst(strtolower($n1));
    $n2 = ucfirst(strtolower($n2));
    $n3 = ucfirst(strtolower($n3));

    return array($n1, $n2, $n3);
  }
```
