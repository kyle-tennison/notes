- `[tk, rem] = strtok(str, d)` will tokenize a string by splitting it at all all delimiters `d`. If no `d` is provided, the space character is used. 
- If strtok starts with a delineating character, it will be ignored and treated as if it doesn't start with one.
	- `strtok('aaaaaaahelloaworld','a')` evaluates to `hello`
- `rem` is the entire rest of the string **after `tk`**, not including `tk` itself.

- Adding a row to a matrix of incompatible size will cause an error.
- Use `strcmp('str', 'check')` to check strings (it's better)
- You can index an entire row/column using `:`
- To unwrap a cell input, you need to index with `{}` instead of `()`.

- Assume you can use any builtin matlab function on a vector
- Don't use `cell2mat` for `strcmp` and other string stuff because this will convert it into one long sting.
	- However, you do need to use it for functions like sum. 
- If you call `vec(x)` when `vec` isn't yet defined, and assign a value to this index, all indices before x will fill.  The same is true for matrices.
- `sort` will automatically use ascending order.
- The order of `sort` can be provided by a second positional argument of `'a'` for ascending or `'d'` descending.
- 
