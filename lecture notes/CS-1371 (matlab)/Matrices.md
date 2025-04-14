## Basics
You can concatenate row vectors horizontally with `[vec1 vec2]`.
You can create a matrix by using `;` to delineate new lines:
`mat = [1 2 3; 4 5 6; 7 8 9]`
```
mat =

     1     2     3
     4     5     6
     7     8     9
```

You can perform element-wise operations with `+ - .* ./`, along with matrix operations `* /`.

You can concatenate row vectors (stack them) into a matrix:
`mat = [vec1; vec2]`
> These vectors must be the same length; otherwise, it will produce an error.

You can transpose a matrix `mat` by adding an apostrophe `mat'`.

The `length()` function on a matrix will find the size of the *largest* dimension.

`sum()`, `prod()`, `mean()`, etc. will perform operations on each column, then return a horizontal vector:

```
>> mat = [1 2 3;
          4 5 6]

mat =

     1     2     3
     4     5     6

>> sum(mat)

ans =

     5     7     9
```

If you want to perform row operations instead of column operations, just transpose the matrix. Alternatively, if the function takes a dimension argument, you could provide it the 2nd dimension. If you provide this dimension argument, then the return type will be in that dimension too.

> If you want to find the sum of all elements in an array, use sum(sum(mat))

## Indexing Matrices 

```matlab
arr = [2 1 3; 6 4 9];

nine = arr(2,3) % matrix(row, col)
nine = arr(end, end)

```

You can linearize a matrix (basically stack all columns on top of each other to create a large column vector), then index it with only one index.
```matlab
vecform = arr(1:end)
vecform = arr(:) % produce the same result
```

>. `1:end` creates a horizontal vector, but `:` will create a column vector

> 🤖 (notecheck comment) - In single index referencing, arr(1:end) also produces a column vector. Both calls yield the same shape in MATLAB, so it’s not correct to say that “1:end” creates a horizontal vector.

In fact, you don't have to actually index this matrix; you can directly try to reference it:
```matlab
% linear indexing
nine = arr(6)
nine = arr(end)
```