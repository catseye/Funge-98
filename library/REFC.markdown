Referenced Cells Extension
==========================

### Fingerprint 0x52454643 ('REFC')

Under development.

The REFC fingerprint allows vectors to be encoded into and decoded from
single scalar cell values.

After successfully loading REFC, the instructions `D` and `R` take on
new semantics.

`R` 'Reference' pops a vector off the stack, and pushes a scalar value
back onto the stack, unique within an internal list of references, which
refers to that vector.

`D` 'Dereference' pops a scalar value off the stack, and pushes the
vector back onto the stack which corresponds to that unique reference
value.

The internal list of references is considered shared among all IP's, so
a global static can be used to store this list, so that this extension
remains tame.
