Orthogonal Easement Library
===========================

### Fingerprint 0x4f525448 ('ORTH')

Under development.

The ORTH fingerprint is designed to ease transition between the
Orthogonal programming language and Befunge-98 (or higher dimension
Funges.) Even if transition from Orthogonal is not an issue, the ORTH
library contains some potentially interesting instructions not in
standard Funge-98.

After successfully loading ORTH, the instructions `A`, `E`, `G`, `O`,
`P`, `S`, `V`, `W`, `X`, `Y`, and `Z` take on new semantics. The
following table, which can be used to translate Orthogonal to Funge-98
and back, includes which Orthogonal instructions they emulate:

        Funge       Orthogonal  Semantic

        +       +       add
        *       *       multiply
        -       -       subtract
        /       /       divide
        %       %       modulo (positive values only)
    >>> A       &       bitwise AND
    >>> O       |       bitwise OR
    >>> E       ^       bitwise EXOR
        !       !       logical negate
        \       ~       swap
        :       @       duplicate
        $       $       pop
        <       L       go west
        >       H       go east
        ^       K       go north
        v       J       go south
        ]       cw      rotate right
        [       ccw     rotate left
        r       rev     reverse
    >>> X       x       change x
    >>> Y       y       change y
    >>> V       dx      change dx
    >>> W       dy      change dy
    >>> G       =       ortho get
    >>> P       #       ortho put
    >>> Z       ?       ramp if zero
        ,       c       output character
    >>> S       s       output string
        .       d       output decimal
        z       nop     no operation
        q       ret     quit
