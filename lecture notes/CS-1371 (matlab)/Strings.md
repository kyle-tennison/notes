Creating a string
```matlab
str = ['a', 'b', 'c']
str = 'abc'
```
These two values will be exactly the same.

You can concatenate multiple strings with:
```matlab
str1 = 'Hello '
str2 = 'world!'

helloWorld = [str1 str2] % equal to HelloWorld
```

To escape an apostrophe:
```matlab
str = 'How's it going' % syntax error
str = 'How''s it going' % written twice; works now
```

You can use the colon operator to generate the alphabet:
```matlab
alphabet = 'a':'z'
```

## Casting
You can cast chars to doubles (via the ASCII table) and vice versa:

```matlab
abc = char([65 66 67]) % equivalent to 'abc'
```
> 🤖 (notecheck comment) - The ASCII values 65, 66, and 67 correspond to 'A', 'B', 'C'. So this snippet yields "ABC", not "abc".

```matlab
doubleArr = double('hello world') % ASCII byte array
```

### Strings to numbers
```matlab
num2str(123) % evaluates to '123'
str2num('123') % evaluates to 123
```

Characters are shallowly hidden ASCII integers, hence, you can do stuff like this:
```matlab
b = char(a+1) % evaluates to 'b'
```

### Capitalizing strings
Lowercase letters are +32 on the ASCII table relative to their uppercase counterparts. Hence, to uppercase a string:
```matlab
helloWorld = 'hello world'

uppercase = char(helloWorld - 32) % HELLO WORLD
```
> 🤖 (notecheck comment) - Subtracting 32 from the space character (ASCII 32) yields ASCII 0 (a null character), not a space. This snippet will not actually produce "HELLO WORLD" with a space. The built-in "upper" function is recommended for robust case conversion.

You can also use the built-in functions:
```matlab
uppercase = upper('hello world')
lowercase = lower('hello world')
```

### Equivalency 
If you want to check if two strings are equal, using the `==` operator will give you a logical array. It is the same as using a plain vector

```matlab
['a' 'b' 'c'] == ['a' 'z' 'c']

% [true false true]
```

Then, to get a single result, use the `all()` function.

### strfind

`strfind(str, pat)` finds the starting index of a substring in a bigger string

```matlab
idx = strfind('hello world', 'world') % 7
```

If there are multiple, you'll get a vector of indices. If there are none, you'll get an empty vector.  

### strcmp

`strcmp(in1, in2) -> logical` - Checks if two strings are the same  
`strcmpi(in1, in2) -> logical` - Checks if two strings are the same (case insensitive)

### contains

`contains(str) -> logical` - Checks if a string contains a substring

### strrep

Replace a string
```matlab
str = 'Hello world!';
str = strrep(str, 'world', 'there');
str % Hello there!
```

# Printing Strings

The `sprintf` function allows you to format a string with `%s` characters like Python.

`%s` - Gets filled with a string  
`%d` or `%i` - For an integer  
`%.nf` - For a float with n (like `%.3f`)  
`%e` or `%E` - Scientific Notation (lowercase and uppercase, respectively)  
`%%`  - For a literal %  
`%g` - Uses either `%f` or `%e`, whichever is shorter