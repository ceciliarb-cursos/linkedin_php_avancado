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
