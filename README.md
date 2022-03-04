# Local-Authority-Districts-2021-neighbours
A lookup of neighbouring and nearby LA districts using 2021 census geographies

<h4>Use</h4>
The objective in creating this dataset was to identify neighbouring places for use in analysis, mapping and robojournalism so that a person reading about a Local Authority will have that LA compared to the most relevant nearby LAs. These are considered to be:
1: those that share boundaries, ordered by the length of the boundary from longest to shortest,
2: those that have boundaries that are close to the subject LA, ordered by distance from the centroid of A to teh boundary of B.

<h4>Structure</h4>
Neighbours that share boundaries are in index [0] of each array. 
Nearby neighbours that do not share boundaries wth the subject are at index >0 of each array.

<h4>Methodology</h4>
Neighbours that share boundaries are ordered by boundary length, with the longest shared boundary appearing first. These have been identified and ordered using QGIS, following the methodology described in this blog:  https://spatialthoughts.com/2020/04/08/calculating-shared-border-lengths/

The LAD codes at index >0 are ordered by proximity from the subject's centroid to the nearest corner of the neighbour's bounding box. They do not include LADs that share boundaries (ie. those included in index 0). These have been calculated by creating bounding boxes for all LADs, then extracting the vertices for these BBs in QGIS. A distance matrix between all centroids and all BB corners has been filtered to find the nearest neighbours. This matrix has been reduced to include only the nearest few local authorities.

<h4>Example: E06000001 - Hartlepool</h4>
<img src="https://user-images.githubusercontent.com/6584653/156748843-7f2355ed-52f2-42c9-85a0-fb821e4948ee.png" width=500></img>

