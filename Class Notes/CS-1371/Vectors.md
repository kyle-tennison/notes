# Vectors

```matlab
my_vec = [10, 20, 30]; % this is the same as saying [10 20 30]

twenty = my_vec(2) % reference the SECOND element (i.e., 20)

% reassignment

vec = [1 8 3 4 5];

vec(2) = 2;

vec % will be [1 2 3 4 5]

vec([1, 2]) = [8, 9];

vec % will be [8 9 3 4 5]

vec([3, 4, 5]) = 0

vec % will be [8 9 0 0 0]

% length

vector_length = length(vec) % will evaluate to 5

% end keyword

last_item = vec(length(vec))

last_item = vec(end) % end gets replaced with length(vec) when it runs

vec2 = 1:1:5 % start:step:end
vec2 = 1:5 % start:end (default step=1)

% indexing with vectors

values = [123,820,1293,12312,29,932];

s = values([1, 3, 5]) % get a vector with the 1st, 3rd, and 5th indicies

% s = [123 1293 29]

values_reverse = values(end:-1:1) % reverses values

vec = [4 9 4 0 4 3 4 5];

vec(1:2:end) = vec(end);

vec
```

- If you want to preform element-wise multiplication, for instance, multiplying each element of one vector with another, you should still use `.*` and `./`
- Putting `[]` in an index is equivalent to deleting that index 
```matlab
vec = [5 2 1]
vec(1) = [] % deletes index 1 (5)

vec = [[] 1 2] % is the same as [1 2]; the [] is disregarded
```

- the `all()` function takes a vector and returns `true` if every value is true
- the `any()` function takes a vector and returns `true` if any value is true


# Boolean Arrays

You can mask boolean arrays with `&` and `|`.

You can use boolean arrays to index vectors. 
```matlab
vec = [9, 2, 1, 7, 0]
vec([true, false false, true, false]) % [9, 7]
```

> True indices are returned, other parts are null