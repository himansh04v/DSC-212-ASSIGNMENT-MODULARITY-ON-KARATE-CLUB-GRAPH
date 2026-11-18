# Modularity on the Karate Club Graph

DSC212: Graph Theory Module, Research Assignment

I implement spectral modularity partitioning from scratch on Zachary's Karate Club
network (34 members, 78 edges). The network is split recursively with the leading
eigenvector of the modularity matrix, and I track how four node metrics change after
each split.

## What the notebook does
- Builds the modularity matrix B = A − kkᵀ/2m and scores partitions with modularity Q
- Splits the graph recursively with the leading eigenvector (Newman, 2006), using the
  generalized modularity matrix for subgroups
- Draws the graph after each split, with one color per community
- Computes degree, betweenness, closeness and clustering after each split and plots
  how they change
- Ends with a short discussion of which nodes stay central

## Results
- First split: 16 and 18 nodes, matching the real club split except for node 8
- Final partition: 4 communities (sizes 7, 9, 12, 6), Q ≈ 0.393

## Files
- `assignment.ipynb`: the notebook (code, outputs, plots, discussion)
- `community_detection.mp4` : animation of steps
- 
## Requirements
- Python 3.9 or newer
- numpy
- networkx
- matplotlib
- imageio-ffmpeg (only for the optional animation cell)
- Jupyter (to open and run the notebook)

## How to run
```bash
pip install -r requirements
jupyter notebook assignment.ipynb
```
Then use Restart & Run All. The notebook runs top to bottom without edits. The last
cell (an animation) is optional and needs `imageio-ffmpeg`. If it isn't installed, that
cell is skipped.

## Reference
M. E. J. Newman, "Modularity and community structure in networks," PNAS 103(23):
8577–8582, 2006.
