# SF2 Image Processing in Python

The Python 3 implementation of the helper functions are in `SF2_Python/helper.py` and `SF2_Python/helper_jpeg.py`.

Some Python functions / methods are project work and they should not provided at the start of the SF2 project.

They are marked after the comment line:

```python
############# Functions not provided initially #############
```

in `helpers.py` and

```python
############# Methods not provided initially #############
```

in `helpers_jpeg.py`.

## PyPI Package Requirements
numpy, scipy, matplotlib, sewar (optional)

## Usage
```python
# Jupyter notebook recommended
# Use %load_ext autoreload
# and %autoreload 2
# in the Jupyter notebook to automatically 
# refresh the imported modules on every run
import numpy as np
import matplotlib.pyplot as plt
from helpers import *
from helpers_jpeg import JpegHuff
jpeg = JpegHuff()

# Use functions before Section 10 of the handout directly
C8 = dct_ii(8)
Y = colxfm(colxfm(X, C8).T, C8).T
draw(beside(X1, X2, X3, X4))  # Improved beside(*args) function
plt.show()  # Optional in Jupyter notebook

# Use the new functions in Section 12 of the handout
# in the JpegHuff class
vlc, _bits, _huffval = jpeg.jpegenc(X-128, qstep)
Z = jpeg.jpegdec(vlc, qstep)
```

For more usage, refer to the project work in the jupyter notebooks in the separate repository.

## Tests

The tests were written in pytest but only have minimum code coverage, so passing the tests does not mean the code base is bug free. Run `pytest` in `SF2_Python/` to run the tests. The code of project work is tested as well.

This repository is provided with no warranty of any kind (MIT license).

## Styling Issues

The comments and doc strings were mostly copied from the old Matlab files and may not comply with good Python styles.
