# Cooper E-80 Equivalent E-Loading Analysis

## Description
This is a python module that allows the user to compare a train loading to the Cooper E-80 train loading, either for a single span, or multiple spans via a matplotlib plot. It computes equivalent E-values for the user defined train based on moment and shear ratios. Requires Python 3. If you don't have Python 3 install it from [here](https://www.python.org/downloads) or preferably using your Linux distribution's package manager. If installing on Windows, make sure you check the box for Tk installation.

## Installation
```
pip install e80analysis
```

## Usage
```python
>>> from e80analysis import E80Analysis
>>> e = E80Analysis()                               # begin an analysis
>>> e.set_spans(range(10, 101))                     # spans set to "range(10, 201)" by default, but can be changed
>>> axle_loads = [35, 35, 35, 35, 35, 35, 35, 35]   # enter train axle loads
>>> axle_spacings = [0, 5, 5, 5, 33.5, 5, 5, 5]     # enter train axle spacings
>>> train = (axle_loads, axle_spacings)             # combine into a tuple
>>> e.span(train, 35)                               # get shear and moment E-values for a single span length
(29.055359246171967, 28.261682242990656)            # these are the equivalent moment and shear E-values for the specified train and span length
>>> e.plot(train)
```

![Example Plot](https://i.imgur.com/igksRp5.png)

The `plot` function can be called with optional argument `save=True` to save a file called 'E-Loading.png' directly in the user's Documents folder rather than display it with tkinter.
