If you are iteration over a vector that is changing size during iteration, the number of iterations will be set when the iterator begins.

```matlab

str = 'testing'

for x = str

	str = [x str]

end

```

This will turn `str` into `[gnitsettesting`

What is a cell array?

# Cell Arrays

A cell array is a way to contain multiple datatypes into an array.

```matlab
cell = {'test', '123', 78};

cell(1) % get the first cell -> {'test'}
cell{1} % get the first cell and unwrap the value -> 'test'  
% You can only use this for one value; use cell2mat to unpack a value; this works regardless of size and is safest

% You can create an empty cell array with:
empty_arr = {};

% You can add items with
empty_arr{1} = 'sample';
empty_arr % {'sample'}

% You can iterate over items with

for value = cell
	fprintf('%s\n', value{:}) % <-- {:} can be used to unpack the value from a cell
end
```

You can recursively add cells to cells; so the following is a valid value:
`{{{{{{{{{{1},2},3},4},5},6},7},8},9},10}`

Appending to a cell array needs to be:
```matlab

cells = {}
for x = 1:10
	cells = [cells {x}]
end

% be careful NOT to do:
for x = 1:10
	cells = {cells x}
end
% this will give you that recusive cell definition where everything is nested.

```
