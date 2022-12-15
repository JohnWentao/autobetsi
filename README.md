Development of automatic application of betsi to a directory of isotherms (`.csv`). 

# Installation

- Follow instructions to install [betsi-gui](https://github.com/nakulrampal/betsi-gui) in a virtual environment.
- clone this repo
- `cd` into the cloned repo, and do `pip install .`

# Basic use

Running `autobetsi` from the command line in a directory `.` runs `betsi` on the contents of `./csv/`. Initial parameters;

| Parameter		| Value		|
| -------------------- 	| ------------- |
| 'max_perc_error' 	| 20.0		|
| 'min_num_pts'		| 10		|
| 'min_r2'		| 0.995		|
| 'use_rouq1'		| True		|
| 'use_rouq2'		| True		|
| 'use_rouq3'		| True		|
| 'use_rouq4'		| True		|
| 'use_rouq5'		| False		|

If an isotherm throws an exception, this typically means that a BET area cannot be found with the current conditions. Any such files are added to a list of exceptions, then reattempted with iteratively reduced `'min_num_points'` until a result is achieved.

Finally, for convenience results are tabulated for each analysis present in `./betsi/` 

# Advanced

The functions in `autobetsi.py` can be imported and used in further scripts.

# TODO

- `betsi` is picky about isotherms. Make cleaning/conversion function.
- Allow use of tags from commandline.
- Silence `betsi`'s warnings from `seaborn`, `matplotlib` etc.

