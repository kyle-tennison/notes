# Exam Notes
- `[tk, rem] = strtok(str, d)` will tokenize a string by splitting it at all delimiters `d`. If no `d` is provided, the space character is used.
- If strtok starts with a delimiter character, it will be ignored and treated as if it does not start with one.
	- `strtok('aaaaaaahelloaworld','a')` evaluates to `hello`
- `rem` is the entire rest of the string **after `tk`**, including `tk`.
> 🤖 (notecheck comment) - The description of "rem" is incorrect. In Matlab, "rem" does not include "tk" but rather starts from the delimiter that ended "tk" through the end of the string.

- Adding a row to a matrix of incompatible size will cause an error.
- Use `strcmp('str', 'check')` to check strings (it's better).
- You can index an entire row/column using `:`.

- Assume you can use any builtin Matlab function on a vector.
- Do not use `cell2mat` for `strcmp` and other string operations because this will convert it into one long string.
	- However, you do need to use it for functions like sum.
- If you call `vec(x)` when `vec` isn't yet defined, and assign a value to this index, all indices before x will be filled. The same is true for matrices.
- `sort` will automatically use ascending order.
- The order of `sort` can be provided by a second positional argument: `'a'` for ascending or `'d'` for descending.

- Do not index multiple values with `{}`. Use `cell2mat(ca)` if you want a numeric array. Index it directly for cell arrays of strings.
- Remember that all items in a struct array must have the same attributes. You can't append something after changing its attribute.
- An array of structs is identical to a struct array.
- `strtok` will return an empty string if there is nothing left to tokenize.

You can flatten a pixel with:
```matlab
pixel = img(y, xi, :);

pixel = pixel(:)';
```

- You can horizontally and vertically concatenate an image, which ends up making the overall image bigger.