
## Syntax
`st = struct(fieldname, value, fieldname2, value2, ...)`

`carInstance = struct('make', 'toyota', 'topSpeed', 120)`
`carInstance.make % toyota`

You can access an attribute by its string variable with:
```matlab
carInstance = struct('make', 'toyota', 'topSpeed', 120)
carInstance.('make') % toyota, you can put anything that will evaluate to a str
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
fieldnames(carInstance)

ans =

  2×1 cell array

    {'make'    }
    {'topSpeed'}
```

The size of one of these structures is 1x1. 