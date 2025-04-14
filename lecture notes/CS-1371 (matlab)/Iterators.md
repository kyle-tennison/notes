If you are iterating over a vector that is changing in size during iteration, the number of iterations is set when the iterator begins.

```matlab
str = 'testing'

for x = str
	str = [x str]
end
```

This will turn `str` into "gnitsettesting"

> 🤖 (notecheck comment) - The final string is "gnitsettesting" with no bracket character included.

What is a cell array?

# Cell Arrays

A cell array is a way to store multiple data types in an array.

```matlab
cell = {'test', '123', 78};

cell(1) % get the first cell -> {'test'}
cell{1} % get the first cell and unwrap the value -> 'test'  
% You can only use this for one value. Use cell2mat to unpack a value; this works regardless of size and is safest.

% You can create an empty cell array with:
empty_arr = {};

% You can add items with:
empty_arr{1} = 'sample';
empty_arr % {'sample'}

% You can iterate over items with:

for value = cell
	fprintf('%s\n', value{:}) % <-- {:} can be used to unpack the value from a cell
end
```

You can recursively add cells to cells; the following is a valid value:
`{{{{{{{{{{1},2},3},4},5},6},7},8},9},10}`

Appending to a cell array should be done as follows:
```matlab
cells = {}
for x = 1:10
	cells = [cells {x}]
end

% Be careful NOT to do:
for x = 1:10
	cells = {cells x}
end
% This will give you that recursive cell definition where everything is nested.
```