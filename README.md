# AOA - Average Over Area (Fortran)

**AOA** (Average Over Area) is a Fortran program designed to calculate the spatial average of surface variables (e.g., temperature, salinity, velocity, etc.) from 2D ASCII text files exported from the MIKE by DHI software (DFS2 format). The result is a time-averaged dataset that can be used for further analysis or plotting.

## Why This Program?

Older versions of MIKE by DHI (e.g., 2014) lacked built-in tools to compute spatial or temporal averages directly from DFS2 files. I wrote this program as part of my thesis work to fill that gap. Hopefully, it can also help others working with oceanographic or environmental modeling data.

---

## Features

- Supports any 2D ASCII export from DFS2 (1 item, 2D only)
- Time series averaging with customizable intervals
- Ignores zero values in averaging (useful for masked/invalid data)
- Generates output text file with averaged values
- Optionally plots output using Gnuplot

---

## How to Compile

Make sure you have `gfortran` installed, then compile the code:

>> gfortran -O2 -o aoa aoa.f90
Then add the executable to your PATH, or keep it in the working directory.

## How to Use

>> aoa [input_filename.txt]
The input should be an ASCII file exported from a DFS2 dataset (2D + time).

The program will prompt for:

the x-boundary (in degrees) for trimming the grid

the time interval (dtimestep) to use for averaging

## Output:

[input_filename]_resault.txt - time-averaged values

Matrix.txt - raw extracted matrix values for certain time steps

plot.plt - gnuplot script for visualization

You can also use:

aoa -h         # Show help
aoa --version  # Show version


## Dependencies
Gnuplot (optional, for plotting output)

## License
Free to use and modify. If you improve it or use it in your work, I’d love to hear about it!

## Author
S. Rasoulpour
Master’s Thesis Tool - 2025

markdown
Copy
Edit
