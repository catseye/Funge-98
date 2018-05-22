Funge-98 ERRATA
===============

Being a collection of lies, damned lies, and statistics about the
[Funge-98 Final Specification](funge98.markdown).

Edition: May 22, 2018.

This document does not aim to list all the ambiguities in the
spec.  There are several instances where some implementors have
interpreted a statement one way, and other implementors have
interpreted it another way.  Such instances may or may not be
listed in this document, but if they are, please do not expect
to find a normative interpretation of them here.

Befunge-93 cells were not unsigned
----------------------------------

Reported by [James Holderness](https://github.com/j4james)
on January 16th, 2016, in
[this GitHub issue](https://github.com/catseye/Funge-98/issues/2).

In the section "Code and Data" the claim is made that
Befunge-93 "defines unsigned 8-bit Funge-Space cells".

In fact, cells in the original Befunge-93 implementation were
`char` type, which ANSI C does not mandate as either signed or
unsigned.  Because the compilers typically used to compile this
code used signed chars, Befunge-93 was popularly understood to
have signed cells, so if you are looking for a de facto standard
for signedness of the cells in Befunge-93, that would probably be
it.  But that's Befunge-93, not Funge-98, anyway.

Incorrect delta for south/north
-------------------------------

Reported by [Bennett Bernardoni](https://github.com/bbernardoni)
on June 21st, 2017, in
[this GitHub issue](https://github.com/catseye/Funge-98/issues/5).

Contra the statement in the section titled "Instruction Pointer",
it is in fact the case that (0,-1) is called _north_ and is
depicted as being more up the page or screen, and (0,1) is called
_south_ and is depicted as being more down the page or screen.
