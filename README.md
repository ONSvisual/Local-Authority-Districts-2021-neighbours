# Local-Authority-Districts-2021-neighbours
A lookup of neighbouring and nearby LA districts using 2021 census geographies

Neighbours that share boundaries are in index [0] of each array. They are ordered by boundary length, with the longest shared boundary appearing first. These have been identified and ordered using QGIS, following the methodology described in this blog:  https://spatialthoughts.com/2020/04/08/calculating-shared-border-lengths/

The LAD codes at index >0 are ordered by proximity from the centroid of the subject's centroid to the nearest corner of the neighbour's bounding box. They do not include LADs that share boundaries (ie. those included in index 0). These have been calculated by creating bounding boxes for all LADs, then extracting the vertices for these BBs in QGIS. A distance matrix between all centroids and all BB corners has been filtered to find the shortest distances. This matrix has been reduced to include only the nearest few local authorities.
