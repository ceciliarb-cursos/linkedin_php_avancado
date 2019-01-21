# Linkedin Curso PHP Avancado
https://www.linkedin.com/learning/advanced-php

## magic methods
https://www.tutorialdocs.com/article/16-php-magic-methods.html

- __construct()
- __destruct()
- __call($funName, $arguments)
- __callStatic($funName, $arguments)
- __get($propertyName)
- __set($property, $value)
- __isset($content)
- __unset($content)
- __sleep()
- __wakeup()
- __toString()
- __invoke()
- __set_state($an_array)
- __clone()
- __autoload($className)
- __debugInfo()


## Iterators
http://php.net/manual/en/spl.iterators.php
- AppendIterator
- ArrayIterator --
- CachingIterator
- CallbackFilterIterator --
- DirectoryIterator --
- EmptyIterator
- FilesystemIterator --
- FilterIterator --
- GlobIterator
- InfiniteIterator --
- IteratorIterator --
- LimitIterator --
- MultipleIterator
- NoRewindIterator
- ParentIterator
- RecursiveArrayIterator
- RecursiveCachingIterator
- RecursiveCallbackFilterIterator
- RecursiveDirectoryIterator --
- RecursiveFilterIterator
- RecursiveIteratorIterator --
- RecursiveRegexIterator
- RecursiveTreeIterator
- RegexIterator

### The SplFileObject class

(PHP 5 >= 5.1.0, PHP 7)

http://php.net/manual/en/class.splfileobject.php
> The SplFileObject class offers an object oriented interface for a file.

## Generators

(PHP 5 >= 5.5.0, PHP 7)

http://php.net/manual/en/language.generators.overview.php
> Generators provide an easy way to implement simple iterators without the overhead or complexity of implementing a class that implements the Iterator interface.

```php
<?php
function fizzbuzz($limit) {
	$i = 0;
	while ($i <= $limit) {
		$yield = null;
		if ($i % 3 == 0) { $yield = 'fizz'; }
		if ($i % 5 == 0) { $yield .= 'buzz'; }
		yield $yield;
		$i++;
	}
	return;
}

foreach(fizzbuzz(25) as $key => $value) {
	echo "{$key} => {$value} \n";
}
```

## Password hash

http://php.net/manual/en/ref.password.php
- password_get_info — Returns information about the given hash
- password_hash — Creates a password hash
- password_needs_rehash — Checks if the given hash matches the given options
- password_verify — Verifies that a password matches a hash

## The Closure class

(PHP 5 >= 5.3.0, PHP 7)

Class used to represent anonymous functions.

1. Exemplo básico
```php
<?php
$array = [1,2,3,4,5,6,7,8,9];
$out = array_filter($array, function($item) {
	return ($item % 2 == 0);
});
print_r($out);
print_r($array);
$filterFunc = function($item) {
	return ($item % 2 == 1);
};
$out = array_filter($array, $filterFunc);
print_r($out);
```

2. Usando ```__invoque```
```php
<?php
class IsPositiveInt {
	public function __invoke($value) {
		return ((int)$value == $value && $value > 0);
	}
}
$invoke = new IsPositiveInt();
var_dump($invoke(5));
var_dump($invoke('5'));
var_dump($invoke(5.0));
var_dump($invoke(-5));
var_dump($invoke(5.1));
```
