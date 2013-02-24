Funge-98 Standard Modes
=======================

### Fingerprint 0x4d4f4445 ('MODE')

Currently under development.

After successfully loading MODE, the instructions `H`, `I`, `Q`, and `S`
take on new semantics, which alter four new states or 'modes' of the
current IP.

`H` toggles an internal flag called hovermode on and off. In hovermode,
the instructions `>`, `<`, `^`, `v`, `|`, and `_` treat the IP's delta
relatively - instead of setting the dx to 0 and dy to -1, `^` would
instead simply subtract 1 from dy.

The `I` "Toggle Invertmode" instruction toggles an internal flag called
*invertmode*. When invertmode is active, cells are **pushed** on the
stack onto the **bottom** instead of the top.

The `Q` "Toggle Queuemode" instruction toggles an internal flag called
*queuemode*. When queuemode is active, cells are **popped** off the
stack from the **bottom** instead of the top.

`S` toggles switchmode on and off. In switchmode, the pairs of
instructions `[` and `]`, `{` and `}`, and `(` and `)` are treated as
switches. When one is executed, the cell it is located in is immediately
overwritten with the other instruction of the pair, providing a
switching mechanism and a way to seperate coincident IP's.
