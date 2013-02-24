Funge-98 Roman Numerals
=======================

### Fingerprint 0x524f4d41 ('ROMA')

After successfully loading ROMA, the instructions `C`, `D`, `I`, `L`,
`M`, `V`, and `X` take on new semantics.

-   `C` pushes 100 onto the stack.
-   `D` pushes 500 onto the stack.
-   `I` pushes 1 onto the stack.
-   `L` pushes 50 onto the stack.
-   `M` pushes 1000 onto the stack.
-   `V` pushes 5 onto the stack.
-   `X` pushes 10 onto the stack.

Note that these are just digits, you still have to do the arithmetic
yourself. Executing `MCMLXXXIV` will not leave 1984 on the stack. But
executing `MCM\-+LXXX+++IV\-++` should.
