# PyTree
**PyTree** is a python package, which you can use to generate trees, realistic or fractal one.
However the whole pricipale is based on fractals.
## Requirements
* Python 2.7+ or 3.x (Recommend)
* Pip
* Pillow
## Installation
### Using Pip
1. Open Terminal
2. Type ```pip3 install Tree```
## Quick Example
### Code
```python
from math import radians
from PIL import Image
from Tree.core import Tree
from Tree.draw import Drawer

if __name__ == "__main__":
    # Create a Tree
    my_tree = Tree(
        pos = (0, 0, 0, -200),
        scale = 0.7,
        complexity = 2,
        angle = (radians(30), 0)
        shift_angle = radians(0),
        sigma = (0.2, 5/180)
    )

    # Let the tree grow
    for i in range(12):
        my_tree.grow()

    # Move the tree in the right position, so that the tree is completly in the image
    rec = my_tree.get_rectangle()
    my_tree.move((-rec[0], -rec[1]))

    # Create a image with the dimensions of the tree
    im = Image.new("RGB", my_tree.get_size())

    # Draw the tree on the image
    Drawer(my_tree, im, (203, 40, 12)+(23, 90, 123), 10).draw()

    # Show the tree
    im.show()
```
### Output
![Example](https://github.com/PixelwarStudio/PyTree/blob/master/images/example.png)
## Further Examples
See [Examples](https://github.com/PixelwarStudio/PyFractalTree/blob/master/examples)
## License
See [License](https://github.com/PixelwarStudio/PyFractalTree/blob/master/LICENSE)
