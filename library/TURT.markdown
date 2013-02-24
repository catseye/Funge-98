Simple Turtle Graphics Library
==============================

### Fingerprint 0x54555254 ('TURT')

Under development.

The TURT fingerprint provides a simple interface to a simple "drawing
turtle-robot simulator".

After successfully loading TURT, several instructions take on new
semantics.

These instructions pop one value off the stack:

-   `L` 'Turn Left' (angle in degrees)
-   `R` 'Turn Right' (angle in degrees)
-   `H` 'Set Heading' (angle in degrees, relative to 0deg, east)
-   `F` 'Forward' (distance in pixels)
-   `B` 'Back' (distance in pixels)
-   `P` 'Pen Position' (0 = up, 1 = down)
-   `C` 'Pen Colour' (24-bit RGB)
-   `N` 'Clear Paper with Colour' (24-bit RGB)
-   `D` 'Show Display' (0 = no, 1 = yes)

These pop two values each:

-   `T` 'Teleport' (x, y coords relative to origin; 00T = home)

These push one value each:

-   `E` 'Query Pen' (0 = up, 1 = down)
-   `A` 'Query Heading' (positive angle relative to east)

These push two values each:

-   `Q` 'Query Position' (x, y coordinates)

These push four values each:

-   `U` 'Query Bounds' (two pairs of x, y coordinates)

And these don't even use the stack:

-   `I` 'Print current Drawing' (if possible)

To keep this fingerprint tame, a single Turtle and display is defined to
be shared amongst all IP's. The turtle is not defined to wrap if it goes
out of bounds (after all this interface might just as well be used to
drive a **real** turtle robot.)
