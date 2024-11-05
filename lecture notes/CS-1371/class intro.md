## Syllabus Notes

Head TA is Rebecca Ho
Course Manager is Aryan Tadwalkar

## Basic Properties
- All numbers are doubles, including integers.
- Booleans are called "logicals"; `true` and `false` (lowercase)
- Chars are denoted with single parenthesis.
- Comments are...
    -  `%` for single lines
    - `%{ ... %}` for multi-lines
- You can clear the interactive console with `>>> clc`

You *can* override a variable to a different type. For example, the following is valid:
```matlab
test = 3;
fprintf("test is:" + test + "\n");
test = 'f';
fprintf("test is:" + test + "\n");
```


Logical Operators in matlab are:
- `&` and
- `|` or
- `~=` not equal
- (and everything else is the same)

**SCALAR** Mathematical Operations:
- `+` addition
- `-` subtraction
- `.*` multiplication
- `./` division
- `.^` exponentiation

> you need to include the `.` prefix to prevent matlab from using matrix operations.

Variable names follow the same rules as python and most other languages.

## Functions

### Function Header

The syntax for a matlab function is:
```matlab
function out = myFunction(arg1, arg2)
	out = arg1 + arg2;
end

new_var = myFunction(3, 5);
fprintf("new var is: " + new_var); % stdout: new var is: 8
```

The variable `out` is like the return type. When the function ends, the out variable is returned. This function is identical to:
```rust
fn myFunction(arg1: f32, arg2: f32) -> f32 {
    arg1 + arg2
}
```

> Notice that we don't need an out variable in other languages; this is a matlab quirk.

If you want to **return multiple values** from a function, you can use the following syntax:

```matlab
function [p2, p4] = plusTwoAndPlusFour(var)
    p2 = var + 2;
    p4 = var + 4;
end

[a, b] = plusTwoAndPlusFour(0); % unwrap the multiple values

fprintf("A: " + a + "; B: " + b)

% stdout: A: 2; B: 4
```


If you want to return no values, there are two ways:
- `function [] = myFunction()`
- `function myFunction()`

## Command Suppressions

If you run an assignment without a semicolon, matlab will print the assignment to the console. There is no programatic difference, only a change in output.

```
>> test = 3

test =

     3

>> test = 3;
```

## Other Quirks

Sometimes booleans will be shown as a logical `1` or `0`. A `1` is true and `0` is false. We are required to write true/false on exams.
```
>> 1 == 1

ans =

  logical

   1
```
'