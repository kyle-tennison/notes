```matlab
name = 'Kantwon';

if name == 'Kantwon' %all([t t t t t t t]) --> true
    out = 'cool';
else
    out = 'not cool';
end

%out would be 'cool'

name = 'kantwon';

if name == 'Kantwon' %all([f t t t t t t]) --> false
    out = 'cool';
else
    out = 'not cool';
end

%out would be 'not cool'
```


This method doesn't always work, so you might have to use `strcmp`. For instance, the following will error because the arrays are different sizes:
```matlab
name = '(Almost) Dr. Kantwon';

if name == 'Kantwon'
    out = 'cool';
else
    out = 'not cool';
end
```


`if`, `else`, and `elseif` are like:
```matlab
function out = calcLetterGrade(num)
	
	if num>=90
		letGrade = 'A'
	elseif num>=80
		letGrade = 'B'
	elseif num>=70
		letGrade = 'C'
	elseif num>=60
		letGrade = 'D'
	else
		letGrade = 'F'
	end
	
	out = sprintf('Your numerical grade is %d which is the letter grade %s',num,letGrade)

end
```

```matlab
%% Basic Syntax

switch var %this variable/value CAN'T be a vector of numbers. However, a string is ok.

	case {thing1, thing2} %if you have multiple things you are checking you have to put them in {}
		DO STUFF
	
	case thing3 %if you only have one thing then the {} are optional
		DO STUFF
	
	%you can have as many 'case' as you want
end
```

### Short Circuiting
`&` and `&&` do the same thing, except if the LHS evaulates to false, then the RHS won't evaluate at all if using `&&`. Using `&` will require both sides to evaulate.
The same is true with `|` vs `||`.