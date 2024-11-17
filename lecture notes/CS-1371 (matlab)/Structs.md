# Structs

## Syntax
`st = struct(fieldname, value, fieldname2, value2, ...)`

`carInstance = struct('make', 'toyota', 'topSpeed', 120)`
`carInstance.make % toyota`

You can access an attribute by its string variable with:
```matlab
carInstance = struct('make', 'toyota', 'topSpeed', 120)
carInstance.('make') % toyota, you can put anything that will evaluate to a str
carInstance.make % exact same
```

You can add an additional field by setting the attribute directly:
```matlab
>>> carInstance = struct('make', 'toyota', 'topSpeed', 120)
>>> carInstance.numWheels = 5
carInstance = 

  struct with fields:

         make: 'toyota'
     topSpeed: 120
    numWheels: 5
```

#### Adding Attributes
You can add attributes to the structure with:
```matlab
>>> st = struct('name', 'liam')
>>> st.age = 14
st = 
  struct with fields:
    name: 'liam'
     age: 14
```

#### Removing Attributes

You can **remove a field/attribute** with the `rmfield`. This creates **a copy** of the structure with the attribute removed.
```matlab
>>> carInstance = struct('make', 'toyota', 'topSpeed', 120)
>>> carInstance2 = rmfield(carInstance, 'make')

carInstance2 = 

  struct with fields:

     topSpeed: 120

```

You can get a cell array (vertical) of the fieldnames in a structure with `fieldnames`:
```matlab
>>> fieldnames(carInstance)

ans =

  2×1 cell array

    {'make'    }
    {'topSpeed'}
```

The size of one of these structures is 1x1. 


### Dynamic Checks

You can use `isfield(st, 'fieldname');` to check if a field exists on a struct. This just like `hasattr` in Python.

You can use `isstruct(st)` to check if a value is of type struct.



### Sized Structures 
You can make a structure with multiple dimensions by providing a cell array as an argument.

```matlab
inst = struct('name', {'John', 'Jim', 'Jake'}, 'age', {23, 31, 19})
```

The size of this cell array would be `1x3`. You will get an error if the dimensions do not match. For example, *the following will error*:

```matlab
inst = struct('name', {'John', 'Jim', 'Jake'}, 'age', {23, 19})
```

^ The dimensions of the name field does not mage the age field. The only *exception* is if the field points to a `1x1`; in this case, it is ok if the dimensions do not match because the value is applied to every instance. The example below is indeed valid, although dimensions are mismatched:
```matlab
inst = struct('name', {'John', 'Jim', 'Jake'}, 'age', 19)
```

Then, you can index the different sub-structures with indices:
```matlab
>> inst(1)

ans = 
  struct with fields:
    name: 'John'
     age: 19

>> inst(2)
ans = 
  struct with fields:
    name: 'Jim'
     age: 19
```

If you were to add a new attribute to one of the sub-structures in a multidimensional, a default attribute of value `[]` would be added to all other instances:
```matlab
>> inst(1).race = 'latino'
>> inst(1)
ans = 
  struct with fields:

    name: 'John'
     age: 19
    race: 'latino'

>> inst(2)
ans = 
  struct with fields:

    name: 'Jim'
     age: 19
    race: []
```

Similarly, if you remove a field from one instance, it will be removed from all other instances.

> My use of the word "instance" isn't great here, but I'm referring to indices of the bigger struct.

#### Quirks

If you **try to index an attribute of the entire structure array**, you would get a 1x1 *of the first attribute*, instead of a list of everything:
```matlab
>> st = struct('name', {'hello' , 'world'})

st = 

  1x2 struct array with fields:

    name


>> val = st.name

val =

    'hello'


>> vals = [st.name]

vals =

    'helloworld'
```

If you want to **concat two structure arrays**, you can effectively treat them as cell arrays:
```matlab
>> st1 = struct('name', {'hello', 'world'})

st1 = 
  1x2 struct array with fields:
    name

>> st2 = struct('name', {'greetings', 'universe'})

st2 = 
  1x2 struct array with fields:
    name


>> big = [st1 st2]

big = 
  1x4 struct array with fields:
    name
```

### `dir` function

The dir function is a matlab builtin that gets info about a directory; if no arguments are provided, it will target the cwd. This function returns a structure array. 

You can collect a cell array from struct attributes all at once using the following syntax:

```matlab
names = {dir(3:end).names} % these curly brakcets are necessary
```

## Manually Constructing Structures

If you assign a value to an attribute of an undefined function, matlab will define that value as an empty struct, then add the corresponding attribute

```matlab
% nothing above this
>>> B.name = 'test'

B = 

  struct with fields:

    name: 'test'

```