---
name: DynamicVisualizations
topic: Dynamic Graphics
maintainer: Dianne Cook, Sherry Zhang
email: dicook@monash.edu
version: 2024-01-05
source: https://github.com/cran-task-views/DynamicVisualizations/
---

One of the strengths of R is the wealth of data plotting packages. This CRAN Task View maintains a list of dynamic graphics packages, for making animations and interactive plots, and links to web resources on plotting data. 

The scope does not include packages focusing on static plots (which is a separate Task View), graphics devices, or packages that have small dynamic graphics components but are primarily focused on other purposes. Note that most of these packages are on CRAN with some on GitHub, Bioconductor, or R-Forge.

If you think that a package is missing from this list, please let us know through issues or pull requests in the [GitHub repository](https://github.com/cran-task-views/VisualizationStatic).

## Table of contents

- [General purpose](#general-purpose)
- [Infrastructure](#infrastructure)
- [Interfaces to other visualization systems](#interfaces-to-other-visualization-systems)
- [Animations](#animations)
- [Maps](#maps)
- [Networks](#networks)
- [Small multiples](#small-multiples)
- [Multivariate](#multivariate)
- [rgl additions](#rgl-additions)
- [Links](#links)

## General purpose

- `r package("ggiraph")` | adopts ggplot syntax for interactive graphics.
- `r package("highcharter")` | R binding to the general purpose highchart JavaScript library.
- `r package("rgl")` |  3D visualization using OpenGL

## Infrastructure

- `r package("crosstalk")` | Tools to get plots to communicate with each other. 
- `r package("shiny")` | Web application creation 

## Interfaces to other visualization systems

- `r package("plotly")` |  interface to plotly for general purpose, and generally allows defining and constructing of new interactive graphics, including linking between plots.
- `r package("rthreejs")` | interface to three.js 
- `r package("htmlwidgets")` | creates R bindings to JavaScript libraries, which underpins many interactive graphics.
- `r package("r2d3")` |  interface to D3 for general purpose 
- `r package("vegalite")` | interface to Vega-Lite javascript framework 
- `r package("vegawidget")` | render Vega-Lite and Vega specifications as htmlwidgets, and to help you communicate with a Vega chart using javascript or Shiny.
- `r package("echarts4r")` | interface to Apache ECharts.
- `r package("rbokeh")` | interface to Bokeh
- `r package("googleVis")` | interface to Google Charts.

## Animations

- `r package("gganimate")` | A layered system for adding interactivity to `r package("ggplot2")` plots.
- `r package("animate")` | A web-based graphics device for animated visualisations, modelled on the `base` syntax, it extends the `base` graphics functions to
  support frame-by-frame animation and keyframes animation.

## Maps

- `r package("leaflet")` and its associates:
    - `r package("leafem")`, `r package("leafgl")` to interface with WebGl,  
    - `r package("leaflegend")` to customise legends
    - `r package("leaflet.multiopacity")` to control the opacity of leaflet layers, 
    - `r package("leaflet.providers")` for provider information on leftlet.js,
    - `r package("leafpop")` for adding graphics, rather than text, in the leaflet popups,
    - `r package("leafsync")` for creating facets/ small multiples
- `r package("mapdeck")` for rendering large map data
- `r package("mapview")` for making quick maps with simple syntax
- `r package("tmap")` as a grammar of graphic for thematic maps (also produce static maps)

## Networks

- `r package("dygraphs")` for time series data
- `r package("networkD3")` to interface D3 network graphics
- `r package("sigmajs")` for network graphics with sigma.js
- `r package("visNetwork")` to interface with vis.js for network

## Small multiples

- `r package("scatterplotmatrix")` for scatterplot matrix based on D3
- `r package("trelliscopejs")` to interface trelliscope.js to view small multiples 

## Multivariate

- `r package("loon")` An extendable toolkit for interactive data visualization and exploration.
- `r package("tourr")` Implements geodesic interpolation and basis generation functions that allow you to create new tour methods from R.
- `r package("spinifex")` Data visualization tours animates linear projection of multivariate data as its basis (ie. orientation) changes.
- `r package("detour")` Portable and performant tour animations built on `r package("threejs")`
- `r package("liminal")` Compose interactive visualisations designed for exploratory high-dimensional data analysis.
- `r package("langevitour")` An HTML widget that randomly tours 2D projections of numerical data.

## rgl additions

-  `r package("rglplus")` | Extra 3D utilities
- `r package("rglwidget")` | `r package("rgl")`" in `r package("htmlwidgets")`" framework
- `r package("shinyRGL")` | Shiny wrappers 
- `r package("plot3Drgl")` | Plotting multi-dimensional data 
- `r package("predict3d")` | Draw 3D predict lot 

### Links

- [Interactive web-based data visualization with R, plotly, and shiny](https://plotly-r.com)
