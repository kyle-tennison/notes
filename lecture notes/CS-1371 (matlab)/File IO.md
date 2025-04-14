# File IO
```matlab
fh = fopen('example.txt') % get a file handle

line = fgetl(fh); % get the first line of the file, broken by \n
line = fgets(fh); % get the second line of the file, broken by \n, but keep the \n character
```

## `fprintf`
You can use `fprintf` to write a formatted string to a file.

```matlab
% 1. open a file with writing permission
fh = fopen('eggnog.txt','w') % <-- creates a file if it doesn't yet exist

fprintf(fh, 'Hello world!') % <--
```
> 🤖 (notecheck comment) - The "fopen('eggnog.txt','w')" line is missing a comma. The correct usage is "fopen('eggnog.txt','w')".

> 🤖 (notecheck comment) - The above note about a missing comma is incorrect. The code "fopen('eggnog.txt','w')" already has the comma and is correct.

## Iterating over lines in a file

If you try to read a line from a file after reaching the end of the file (using `fgetl` or `fgets`), these functions will return a double value of `-1`. So, if you want to iterate over the contents, you can say:
```matlab
line = fgetl(fh)
while ischar(line)
	
	% do stuff

	line = fgetl(fh) % proceed to next line
end
```