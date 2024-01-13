---
name: DynamicVisualizations
topic: Dynamic Graphics
maintainer: Dianne Cook, Sherry Zhang
email: dicook@monash.edu
version: 2024-01-05
source: https://github.com/cran-task-views/DynamicVisualizations/
---

One of the strengths of R is the wealth of data plotting packages. This CRAN Task View maintains a list of dynamic graphics packages, for making animations and interactive plots.

Static plots are not within the scope of this CRAN Task View, neither are graphic devices. Domain-specific packages with merely one or two functions to produce interactive plots or animation may not be included. 

If you think that a package is missing from this list, please let us know through issues or pull requests in the [GitHub repository](https://github.com/cran-task-views/DynamicVisualizations).

# General purpose

A collection of interactive visualisation pacakges in R are powered by Javascript via `htmlwidgets`. 

  - `r pkg("ggiraph", priority = "core")` provides ggplot2-inspired syntax like `geom_xxx_interactive()` to add tooltips and customised interactive effects.
  - The package `r pkg("crosstalk", priority = "core")` creates linked plots for brushing and filtering through a *SharedData* object. For temporal data, `r pkg("tsibbletalk")` creates shared tsibble objects to produce linked plots.
  - Packages that wrap the Javascript visualisation library: 
    - *plotly*: Static plots created from ggplot2 can be turned into an interactive plot via the `r pkg("plotly", priority = "core")` function `ggplotly()` 
    - *D3*: The function `r2d3()` in `r pkg("r2d3")` binds an R data object to a D3 JS script.
    - *Vega/ Vega-Lite*: The `r pkg("vegawidget")` package takes a vega specification (can be created from a list in R via `as_vegaspec()`). The `r pkg("altair")` package interfaces to the Python altair package that interfaces to Javascript Vega-Lite.
    - *Highcharts*: `r pkg("highcharter")` provides quick syntax for plotting a range of native R objects, including `data.frame`, `ts`, `xts`, `forecast`, and `survfit`.
    - *Apache ECharts*: `r pkg("echarts4r")`, similarly `r pkg("echarty")`
    - *Google Charts*: `r pkg("googleVis")`
    - `r pkg("metricsgraphics")` interfacing to MetricsGraphics.js D3 chart library
    - `r pkg("billboarder")` interfacing to billboard.js D3 chart library, under D3. 
    - `r pkg("rAmCharts")` and `r pkg("rAmCharts4")`

While most dynmaic visualization in R is created through interfacing to Javascript, an alternative method is to iterate through static frames (frame-by-frame looping).

  - `r pkg("gganimate", priority = "core")` built on top of `ggplot2` to create animation. 
  - `r pkg("animate")` | A web-based graphics device for animated visualisations, modelled on the `base` syntax, it extends the `base` graphics functions to support frame-by-frame animation and keyframes animation.

# Multivariate

One of the most common visualisations for high dimension data is scatterplot matrix. It can be created with `GGally::ggpairs()` and turned into interactive using `plotly::ggplotly()` to enable linked brushing to view the data at different variable combinations. The `r pkg("pairsD3")` package creates scatterplot matrices through D3 javascript library. 

When the multivariate relationship is attributed to more than two variables, a scatterplot matrix becomes insufficent and a family of technique, called tour, can be useful to explore the structure in high dimensional data. The tour technique animates a sequence of linear projections of high dimensional data and it has two components: 1) tour type: how the projection sequence is generated, and 2) display: how low-D projections are displayed. Different tours are available to select the projection sequences (grand tour: random selection, guided tour: based on projection pursuit, etc). The most common display is histograms for 1D projections and scatterplot for 2D projections. Other higher-D displays are also available, including the Chernoff face. 

- `r pkg("tourr")` implements varies tourr types (`grand_tour`, `guided_tour`, `planned_tour`, `local_tour`, etc) and displays (`animate_xy`: 2D, `animate_dist`: 1D, etc) to create frame-by-frame animation. 
- `r pkg("spinifex")` implements the manual tourr algorithm (`manual_tour`)
- `r pkg("liminal")` implements linked display view to understanding embedding algorithms such as tSNE through `r pkg("vegawidgets")`
- `r pkg("detourr")` implments the 2D and 3D scatterplot display with three.js for better interactive manipulations (rotation, pan, selection, brushing with color and time control)
- `r pkg("langevitour")` implements the langevin dynamics to generate projection sequence and builds the display with D3.js

Another class of interactive visualisation in R is the `r pkg("loon")` toolkit. The graphic system is written in TCL and accessed in R via the `tcltk` package. 

# Maps

For general purpose, the `r pkg("leaflet", priority = "core")` package provides an R interface to the leaflet Javascript library and a collection of packages are available for additional customisation:

  - `r pkg("leafpop")` allows static plots to be displyaed in the leaflet popups,
  - `r pkg("leafsync")` displays multiple synced leaflet maps in small multiples,
  - `r pkg("leaflegend")` adds customised images as marks and in the legend, 
  - `r pkg("leaflet.multiopacity")` provides controls the opacity over different plot layers
  - `r pkg("leafem")` supports GIS-related layers, (e.g. Cloud Optimised Geotiff (COG), stars/rasters images), to leaflet map,
  - `r pkg("leafgl")` has the capacity to render large scale data (e.g. 1 million points or 100k polygons) in leaflet with the WebGL framework,
  - `r pkg("leaflet.minicharts")` renders glyphs on leaflet maps.
  - `r pkg("mapedit")` provides interactive editing on leaflet maps

For exploratory data analysis, it comes handy to able to create maps quickly with short syntax to plot the geospatial data. `r pkg("mapview")` is such a package for creating quick leaflet and mapdeck maps from common spatial classes in R (`sf`, `raster`, `stars`, etc). 

When working with large scale spatial data, graphic libraries are usually used for rendering maps and this includes 1) `r pkg("mapboxer")` via Mapbox, 2) `r pkg("deckgl")` via Deck.gl, and 3) `r pkg("mapdeck")` via Mapbox GL and Deck.gl.
  
The `r pkg("tmap")` package proposes a new grammar tailored for thematic maps (both static and interactive) and leaflet is used for interactive map rendering.

# Networks and trees

Package interfacing with Javascript libraries to plot networks diagrams includes 

  - `r pkg("networkD3")` to create D3 network diagrams (force directed networks, sankey diagrams, radial networks, and dendrogram)
  - `r pkg("visNetwork")` that provides interfaces to vis.js
  - `r pkg("sigmajs")` that interfaces with sigma.js

All three packages can convert native R data frames or igraph objects into network diagrams powered by their corresponding Javascript libraries. The packages `r pkg("networkD3")` and `r pkg("visNetwork")` use a single-line command for quick plotting, while `r pkg("sigmajs")` takes a structured grammar to build the networks.

The `r pkg("collapsibleTree")` package allows users to click on tree nodes to expand and collapse complex trees through D3.js in the backend.

# Miscellaneous

R also includes packages dedicated to specific interactive visualizations, often by interfacing with relevant JavaScript libraries.

  - temporal: `r pkg("dygraphs")` (dygraphs.js)
  - small multiples: `r pkg("trelliscopejs")` (trelliscope.js) 
  - heatmap: `r pkg("heatmaply")` (plotly.js), `r pkg("d3heatmap")` (D3.js), `r pkg("iheatmapr")` (plotly.js).
  - parallel coordinate plot: `r pkg("parallelPlot")` (d3.js)
  - timeline: `r pkg("timevis")`  (vis.js) 
  - upset plot: `r pkg("upsetjs")` (upset.js)
  
# Links

- Book: [Interactive web-based data visualization with R, plotly, and shiny](https://plotly-r.com)
- Book: [Javascript for R](https://book.javascript-for-r.com/)
- Book: [Interactively exploring high-dimensional data and models in R](https://dicook.github.io/mulgar_book/)
