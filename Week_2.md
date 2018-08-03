# Week 2 Workbook

## Project Introduction

Microscopium is an openly developed project aiming to provide a tool for clustering high content images. Currently the project is using PCA to reduce the feature space to a two dimensional plot of the images. The images can then be selected for further inspection.

The datasets being used currently are based on microscopic images of cells undergoing a variety of treatments (e.g. gene therapy, drugs). The images are thresholded and then uninformed features such as shape, intensity and variance are fed into PCA. 

The initial results have been promising, with a few unlabelled treatments being correctly clustered together with their compounds.

## Improvements

The ultimate goal of the project is to provide a system where a large dataset can be input by an IT layman and, with minimal interaction and parameter selection, be displayed on the Bokeh web app for inspection. 

Currently parameters are still being specified manually in a number of cases, particularly in the initial processing of the images. This is a major roadblock to streamlining the entire process.

Additionally, UI & UX work could be done to add more functionality such as
* Labels display when you hover over a point
* Colour-coded treatments
* Saving a selection
* Displaying feature distributions based on given selections

In the back-end:
* UMAP is a new dimensionality-reduction algorithm with purported superior run time performance and greater global structure preservation than t-SNE. Implementing UMAP would be highly useful
* Considering clustering based on the distances between treatments e.g. you would assume two copies of a control cell to be distributed closely together on the plot, with all other cells being further away. A CNN could be used to determine the distances between treatments, before clustering.

## Current Tasks
* Draga & James will work on getting their own data set running on the Bokeh app
* Draga & James will see if there are any similar projects/papers out there

