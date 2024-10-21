# Julia Data Cubes

## Overview

- Storage and analysis of large geospatial raster data e.g. Satellite imagery
- Focus on high throughput computing (HTC) limited by data loading
- Array with dimensions e.g. lon, lat, and time, instead of a list of points in vector data
- Cloud optimized to access particular slices of the data (e.g. Bounding box or timespans)
- Importance of data compression for cloud-optimized workflows
- Workflow specific optimization using chunking
- Lazy computations on large data and making data cubes AI-ready


## Featured Projects

- [YAXArrays.jl](https://github.com/JuliaDataCubes/YAXArrays.jl)
- [PyramidScheme.jl](https://github.com/JuliaDataCubes/PyramidScheme.jl)
- [EarthDataLab.jl](https://github.com/JuliaDataCubes/EarthDataLab.jl)
- [DGGS.jl](https://github.com/danlooo/DGGS.jl)
- [DiskArrays.jl](https://github.com/meggart/DiskArrays.jl)
- [Zarr.jl](https://github.com/JuliaIO/Zarr.jl)

<hr>
[Imprint](https://www.bgc-jena.mpg.de/2299/imprint)
<script src="http://code.jquery.com/jquery-1.4.2.min.js"></script> <script> var x = document.getElementsByClassName("site-footer-credits"); setTimeout(() => { x[0].remove(); }, 10); </script>