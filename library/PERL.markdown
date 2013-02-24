Generic Interface to the Perl Language
======================================

### Fingerprint 0x5045524c ('PERL')

Under development.

The PERL fingerprint is designed to provide a basic, no-frills interface
to the Perl language.

After successfully loading PERL, the instructions `E`, `I`, and `S` take
on new semantics.

`S` ('Shelled') pushes a 0 on the stack if the Perl language is already
loaded (e.g. the interpreter is written in Perl). It pushes a 1 on the
stack otherwise, indicating that the Perl language will be shelled when
needed.

`E` ('Eval') pops a 0gnirts string and performs a Perl `eval()` on it,
possibly (or not) shelling Perl as indicated by S above. The result of
the call is pushed as a 0gnirts string back onto the stack.

`I` ('Int Eval') acts the same as `E`, except that the result of the
call is converted to an integer and pushed as a single cell onto the
stack.
