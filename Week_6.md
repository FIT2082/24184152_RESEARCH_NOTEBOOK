# Week 6

This week was focused on finishing the code to process one of the 55 BBBC021 zip archives into the Bokeh app. We added code to stitch and stack the images, extract the features and perform dimension reduction using PCA. We now have the coordinates of each image and they are loading into Bokeh, with some issues still existing as below.

## Remaining Script
The parts of the script using stitching and stacking the images have been changed to use the montage_stream function now, which performs the stacking and stitching operation on an entire folder of images, making things much easier. We've also made sure to keep track of any non-default inputs, such as directory paths and filenames in constant fields, as these would represent the minimum input required to produce a working instance of the Bokeh app from a set of images.

## Multiple Image Loading
Although single images seem to be loading fine into Bokeh, multiple images don't load correctly. The images are "plotted" pixel by pixel onto the xy axes of the right hand side of the page. This means some transformations must be performed between reading the images into numpy arrays and plotting them. It seems that these transformations are not being performed correctly for our images, even though the test dataset loads multiple images just fine. This will require Juan's help.

## Directory Structure
One thing we need to clarify is the directory structure we should be keeping. Currently the BBBC code lives in the same directory as the microscopium code, but it's clear that microscopium should work separately either as a cli or part of a package install. We will need to clarify with Juan how exactly we should use microscopium to make sure that our scripts are separate from the microscopium source code itself.
