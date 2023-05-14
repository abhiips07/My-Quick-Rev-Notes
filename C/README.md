### scanf()
return no of bytes read

Syntax:
```
%[*][width][modifier]type

*			only reads and suppresses or ignore the assignment to any variable
width		MAXIMUM no of character to read
modifier	h : short or unsigned int, l : long int, L : long double
type
			%c							for single character
			%d, %i						for integer values
			%e, %E, %f, %g, %G			for floating point numbers
			%o							for octal numbers
			%x, %X						for hexadecimal values
			%u							for unsigned integer values
			%s							for sequence of characters
```
%\[^\n\] in scanf to read whole line till newline is encountered

### printf()
returns no. of bytes written

Syntax:
```
%[flags][width][.precision][modifier]type

flags
	-	Left justify
	+	data with numeric sign
	#	for additional prefixes like o, x, X, 0, 0x, 0X for octal or hexadecimal
	0	number is left-padded with zeros (0) instead of spaces.
width	MINIMUM	no positions to occupy
.precision	no of digit after decimal OR max no of character of a string
```