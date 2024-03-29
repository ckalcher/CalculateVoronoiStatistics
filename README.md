# Calculate Voronoi statistics
This *OVITO* [Python modifier](https://docs.ovito.org/python/introduction/custom_modifiers.html) generates a histogram of the Voronoi motifs generated by the 
[Voronoi analysis modifier](https://www.ovito.org/docs/current/reference/pipelines/modifiers/voronoi_analysis.html) 
sorted by occurence.

## Description
This modifier can compute a histogram of the Voronoi index of each Voronoi cell in your data collection, where each Voronoi index is a vector of integers indicating the number of edges on each face of the Voronoi polyhedron: `<n_1, n_2, ...,n_max-face-order>`.
The output is a histogram of the Voronoi motifs in your structure ordered by frequency.
You have some control over the appearance of the histogram labels, but note that when generating the histogram, always the full Voronoi signature of a Voronoi cell is used.

## Parameters 
- `max_indices` / "Show N most frequent motifs": Controls the number of bars in the bar graph.
- `y_axis_format` / "y-axis format: Absolute / Relative": Choose wether to display the absolute or relative count on the y-axis of the histogram.
- `x_axis_labels` / "Truncate x-axis labels": Lets you choose wheter to shorten the Voronoi indices in the x-axis labels. If disabled labels will look like this: `<n_1, n_2, ...,n_max-face-order>`
- `n_start` / "Min Voronoi order": The start Voronoi index used in x-axis labels `<n_start,...,n_end>` (only if option `Truncate x-axis labels` is selected.)
- `n_end` / "Max Voronoi order": The end Voronoi index used in x-axis labels `<n_start,...,n_end>`
 (only if option `Truncate x-axis labels` is selected.)
- `use_selected` / "Use only selected atoms": Use only the Voronoi signatures of selected atoms to generate the histogram.


## Example
![Screenshot of OVITO Pro Desktop application](./Examples/CalculateVoronoiStatisticsModifier.png)

## Installation
- OVITO Pro built-in Python interpreter
```
ovitos -m pip install --user git+https://github.com/ckalcher/CalculateVoronoiStatistics.git
``` 
- Standalone Python package or Conda environment
```
pip install --user git+https://github.com/ckalcher/CalculateVoronoiStatistics.git
```
- Please note that the `--user` tag is recommended but optional and depends on your Python installation.

## Technical information / dependencies
- Tested on OVITO version 3.9.1

## Contact
Constanze Kalcher kalcher@ovito.org
