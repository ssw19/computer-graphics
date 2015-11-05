# CG - Matrix Paint

* Repository: [github.com/lucasdavid/Matrix-Paint](https://github.com/lucasdavid/Matrix-Paint)
* Language: Java
* Authors:
  * [Diorge Brognara](https://github.com/diorge)
  * [Fábio Gunkel](https://github.com/Chuckrute)
  * [Lucas David](https://github.com/lucasdavid)

## Introduction

Drawing of elementary geometric forms using OpenGL.

In special, 2D lines using the [Midpoint Line Algorithm](http://www.mat.univie.ac.at/~kriegl/Skripten/CG/node25.html),
polygons (which are dealt here as, essentially, collections of lines) and circles using
[Bresenham's Circle Algorithm](http://web.engr.oregonstate.edu/~sllu/bcircle.pdf).

Additionally, forms are being filled with the [Scan-line Algorithm](https://github.com/lucasdavid/Matrix-Paint/blob/master/src/org/CG/infrastructure/ScanLineAlgorithm.java).

## Installing and running

If you're having problems installing or executing this project,
follow this [steps](https://github.com/lucasdavid/Matrix-Paint/blob/master/INSTALL.md).

## Usage

### Drawing
#### Lines
Click and hold the `left mouse-button`, dragging it to the end of the `line`.
Finally, release the button.

#### Circles and circumferences
Click and hold the `left mouse-button`. Dragging it away from the origin will increase the `radius`
of the form. Releasing the button will then commit it.

#### Polygons
`Polygons` can have their sides drawn in the exact same manner as you would draw a `line`.
Once you release the `left mouse-button`, though, you have two options:

* Click and hold the `left mouse-button` again, creating a line that starts at the end of the previous one.
* Click with the `right mouse-button`, commiting the form. If the form is disconnected,
a new line will be drawn between the end coordinate of the last side and the first coordinate
of the first one.

An alternative way to draw polygons is to hold the `left mouse-button` the whole time,
right-clicking when you want to add a vertex to the polygon. Finally, release the left button
and click with the right one to commit the polygon.

#### Rectangles

Click and hold the `left mouse-button`. Dragging it away from the origin `(0, 0)` will form the rectangle
from the two vectors `(x, 0)` and `(0, y)`.

#### Squares

`Squares` can be drawn similarly to rectangles, except that only one of the vectors `(x, 0)` and `(0, y)`
is considered for its size increase/decrease (the one with greater norm).

#### Pencil

Move the mouse and `left click` onto the canvas wherever you want to brush it. Of course, you can simply
hold the `left mouse-button` and drag the mouse.

### Undoing and redoing
You can undo/redo by rotating the mouse wheel.

### Moving structures
The last structure added is translated when dragging the mouse with the `left mouse-button` and `ctrl` pressed.

### Coloring
Random colors are selected for each drawing. You may use `Color` option in the main menu bar and click `Pick`
to bring up a color picker. The picked color will be used for every drawing therefore. To returning back
to the random color behavior, click `Color` in the main menu bar, and then click `Random`.

## Extending

### Implementing new drawings

Classes inside the package `org.CG.drawings` are automatically scanned and loaded for usage.
To implement new drawings, simply declare a new class in the package,
extend `Drawing` and implement its abstract methods.