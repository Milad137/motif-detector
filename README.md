# Motif Detector

[![Motif detector](https://miro.medium.com/v2/resize:fit:1100/format:webp/0*ho9boRhYdxOvqrJD.png)](http://alumni.cs.ucr.edu/~mueen/pdf/EM.pdf)

**Exact Discovery of Time Series Motifs**

Discover recurring patterns (motifs) in 1-D time series using a modified version of the algorithm described in [Mueen et al., EMMA](http://www.cs.ucr.edu/~mueen/pdf/EM.pdf).
It uses Pandas and returns motifs as a structured **DataFrame**.

## Features

* Detect motifs in a 1-D time series (`pandas.Series`).
* Cross-platform support: Windows, Linux, macOS.
* Handles permissions and prompts installation for `wine` on non-Windows systems.
* Returns motifs in a **hierarchical DataFrame** with groupings and motif indices.

## Input Parameters

| Parameter      | Type        | Description                                            |
| -------------- | ----------- | ------------------------------------------------------ |
| `data`         | `pd.Series` | One-dimensional time series input.                     |
| `motif_length` | `int`       | Length of each motif subsequence.                      |
| `major_factor` | `float`     | Major factor of cluster radius (>1 and >minor_factor). |
| `minor_factor` | `float`     | Minor factor of cluster radius (>1).                   |

## Output

| Output   | Type           | Description                                                                                                         |
|----------|----------------|---------------------------------------------------------------------------------------------------------------------|
| `motifs` | `pd.DataFrame` | DataFrame containing all discovered motifs. Columns are hierarchical: **Group**, **Number**, **Id**, and **value**. |
| `bsfb`   | `float`        | Final Euclidean distance (best-so-far break) computed by the algorithm.                                             |

**DataFrame structure example**:

```
Group | Number | Id | value
------|--------|----|------
0     | 0      | 0  | 1.23
0     | 0      | 1  | 1.45
0     | 1      | 0  | 2.01
...
```
