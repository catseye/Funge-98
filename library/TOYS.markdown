Funge-98 Standard Toys
======================

### Fingerprint 0x544f5953 ('TOYS')

Under development.

After successfully loading TOYS, the instructions `A`, `B`, `C`, `D`,
`E`, `F`, `G`, `H`, `I`, `J`, `K`, `L`, `M`, `N`, `O`, `P`, `Q`, `R`,
`S`, `T`, `U`, `V`, `W`, `X`, `Y`, and `Z` take on new semantics (and
INTERCAL-esque names).

`C` ('bracelet') pops three vectors off the stack and performs a
low-order copy of Funge-Space.

`K` ('scissors') pops three vectors off the stack and performs a
high-order copy of Funge-Space.

`M` ('kittycat') pops three vectors off the stack and performs a
low-order move (copy & erase original) of Funge-Space.

`V` ('dixiecup') pops three vectors off the stack and performs a
high-order move of Funge-Space.

`S` ('chicane') pops two vectors off the stack, then a cell, then fills
that area of Funge-Space homogenously with that cell's value.

Which order a copy or move takes is important if you copy or move to an
overlapping area. Ensure when implementing these that the order is
preserved in all dimensions.

The first two vectors are like the arguments to `o`. In all except `S`,
the third is the destination, relative to the origin.

`J` ('fishhook') pops a value off the stack, and causes the current
column (y coordinate) of Funge-space to be translated north (if value is
negative) or south (if positive) that many rows.

`O` ('boulder') pops a value off the stack, and causes the current row
(x coordinate) of Funge-space to be translated west (if value is
negative) or east (if positive) that many columns.

`L` ('corner') works like `'` except it picks up the cell to the "left"
of the IP's line and does not skip over anything. (Historians may note
that this works like "Get Left Hand" did in Befunge-97.) The cell to the
"left" of the IP is the IP's position, plus its delta rotated -90
degrees about the Z axis (a la `[`)

`R` ('can opener') is a corresponding instruction that mirrors `L` and
works to the right, rotated 90 degrees about the Z axis ("Get Right
Hand" from Befunge-97)

`I` ('doric column') pops a value off the stack, increments it, and
pushes it back onto the stack.

`D` ('toilet seat') pops a value off the stack, decrements it, and
pushes it back onto the stack.

`N` ('lightning bolt') pops a value off the stack, negates it, and
pushes it back onto the stack.

`H` ('pair of stilts') pops a value *b* off the stack, then a value *a*,
then binary-shifts *a* *b* places left if *b* is positive, or |*b*|
places right if *b* is negative.

`A` ('gable') pops a cell *n* off the stack, then another cell, then
pushes *n* copies of that cell onto the stack.

`B` ('pair of shoes') pops two cells off the stack and pushes the result
of a "butterfly" bit operation.

`E` ('pitchfork head') pops all values off the stack and pushes their
sum back onto it.

`P` ('mailbox') pops all values off the stack and pushes their product
back onto it.

`F` ('calipers') pops a vector, then a value *i*. Treating the rest of
the stack as *j* groups of *i* cells each, it writes this 2D matrix into
Funge-space in row-major order, with it's least point as the given
vector.

`G` ('counterclockwise') pops a vector, then a value *i*. It then pushes
onto the stack *j* groups of *i* cells each which it retrieves as a 2D
matrix in Funge-space in row-major order, the least point of which being
the vector supplied to it.

`Q` ('necklace') pops a value off the stack and places it into the cell
directly behind the IP (kind of like `s`, except behind, and no cell is
skipped over.)

`T` ('barstool') pops a dimension number off the stack; if it's a 0,
acts like `_`; if it's 1, acts like `|`; if it's 2, acts like `m`; etc.
depending on the number of available dimensions as appropriate of
course.

`U` ('tumbler') is like `?` but one-shot. When executed, it randomly
transmutes into one of `<`, `>`, `^`, `v`, `h`, or `l`, depending on the
number of available dimensions as appropriate of course.

`W` ('television antenna') pops a vector off the stack, then a value. If
the cell at that vector (plus the storage offset) in Funge-Space (a la
`g`) is equal to that value, nothing happens. If the cell in space is
less than the value, it pushes the value and the vector (inverted) back
onto the stack, and backs up the IP (subtracts the IP's delta from it's
position, sort of a 'wait to try again' condition, useful mainly in
Concurrent Funge.) If the cell in space is greater than that value, acts
like `r`.

`X` ('buried treasure') increments the IP's x coordinate.

`Y` ('slingshot') increments the IP's y coordinate.

`Z` ('barn door') increments the IP's z coordinate.

These three instructions are useful at the end of a line, to indicate
"proceed to next line then wrap". Note the IP's delta motion is still
fully in effect.
