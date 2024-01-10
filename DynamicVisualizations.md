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

### General purpose

A collection of interactive visualisation pacakges in R are powered by Javascript via `r pkg("htmlwidgets")`. 

- `r pkg("ggiraph")` provides ggplot2-inspired syntax like `geom_xxx_interactive()` to add tooltips and customised interactive effects.
- The package `r pkg("crosstalk")` creates linked plots for brushing and filtering through a *SharedData* object. For temporal data, `r pkg("tsibbletalk")` creates shared tsibble objects to produce linked plots.
- Packages that wrap the Javascript visualisation library: 
  
  - *plotly*: Static plots created from ggplot2 can be turned into an interactive plot via the `r pkg("plotly")` function `ggplotly()` 
  - *D3*: The function `r2d3()` in `r pkg("r2d3")` binds an R data object to a D3 JS script.
  - *Vega/ Vega-Lite*: The `r pkg("vegawidget")` function `vegawidget()` takes a vega specification (can be created from a list in R via `as_vegaspec()`).
  - *Highcharts*: `r pkg("highcharter")` provides quick syntax for plotting a range of native R objects, including `data.frame`, `ts`, `xts`, `forecast`, and `survfit`.
  - *Apache ECharts*: `r pkg("echarts4r")` 


- `r pkg("rgl")` |  3D visualization using OpenGL
  
  - `r pkg("rglplus")` | Extra 3D utilities
  - `r pkg("rglwidget")` | `r pkg("rgl")`" in `r pkg("htmlwidgets")`" framework
  - `r pkg("shinyRGL")` | Shiny wrappers 
  - `r pkg("plot3Drgl")` | Plotting multi-dimensional data 
  - `r pkg("predict3d")` | Draw 3D predict lot 

## Animations

- `r pkg("gganimate")` | A layered system for adding interactivity to `r pkg("ggplot2")` plots.
- `r pkg("animate")` | A web-based graphics device for animated visualisations, modelled on the `base` syntax, it extends the `base` graphics functions to support frame-by-frame animation and keyframes animation.

## Maps

- `r pkg("leaflet")` and its associates:
    - `r pkg("leafem")`, `r pkg("leafgl")` to interface with WebGl,  
    - `r pkg("leaflegend")` to customise legends
    - `r pkg("leaflet.multiopacity")` to control the opacity of leaflet layers, 
    - `r pkg("leaflet.providers")` for provider information on leftlet.js,
    - `r pkg("leafpop")` for adding graphics, rather than text, in the leaflet popups,
    - `r pkg("leafsync")` for creating facets/ small multiples
- `r pkg("mapdeck")` for rendering large map data
- `r pkg("mapview")` for making quick maps with simple syntax
- `r pkg("tmap")` as a grammar of graphic for thematic maps (also produce static maps)

## Networks

- `r pkg("dygraphs")` for time series data
- `r pkg("networkD3")` to interface D3 network graphics
- `r pkg("sigmajs")` for network graphics with sigma.js
- `r pkg("visNetwork")` to interface with vis.js for network

## Small multiples

- `r pkg("scatterPlotMatrix")` for scatterplot matrix based on D3
- `r pkg("trelliscopejs")` to interface trelliscope.js to view small multiples 

## Multivariate

- `r pkg("loon")` An extendable toolkit for interactive data visualization and exploration.
- `r pkg("tourr")` Implements geodesic interpolation and basis generation functions that allow you to create new tour methods from R.
- `r pkg("spinifex")` Data visualization tours animates linear projection of multivariate data as its basis (ie. orientation) changes.
- `r pkg("detourr")` Portable and performant tour animations built on `r pkg("threejs")`
- `r pkg("liminal")` Compose interactive visualisations designed for exploratory high-dimensional data analysis.
- `r pkg("langevitour")` An HTML widget that randomly tours 2D projections of numerical data.

### Links

- Book: [Interactive web-based data visualization with R, plotly, and shiny](https://plotly-r.com)
- Book: [Javascript for R](https://book.javascript-for-r.com/)
