# File IO
```matlab
fh = fopen('example.txt') # get a file handle

line = fgetl(fh); % get first line of file, broken by \n
line = fgets(fh); % get second line of file, broken by \n, but keep \n char
```

## `fprintf`
You can use `fprintf` to write a formatted string to a file.


```matlab
% 1. open a file with writing permission
fh = fopen('eggnog.txt' 'w') % <-- creates a file if it doesn't yet exist

fprintf(fh, 'Hello world!') <-- 
```

## Iterating over lines in a file

If you try to read a line of a file with `fgetl` or `fgets` after the entire content of the file, these functions will return a double of `-1`. So, if you want to iterate over the contents, you can say:
```matlab
line = fgetl(fh)
while ischar(line)
	
	% do stuff

	line = fgetl(fh) % proceed to next lien
end
```

