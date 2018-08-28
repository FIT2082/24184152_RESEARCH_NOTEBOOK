# Week 5

This week has been mainly dedicated to writing a Python script which processes the BBBC dataset we will use to assess the classification
ability of Microscopium. The goal is to have one individual script which given a directory path and a minimal number of other arguments e.g.
desired filename formats, output directories or level of compression, is able to process a folder of HCS images into a CSV containing the
required information for the Bokeh app: (x,y) coordinates for each point and the filename of the photo corresponding to each point. 

## The BBBC021 Dataset
BBBC (Broad Bioimage Benchmark Collection) datasets are collections of microscopic images with descriptions of each set's biological applications
and some "expected truth" about the data. The datasets are designed as easy reference points when researchers develop new analysis algorithms
for the biological sciences.

The dataset we are using is the BBBC021 dataset which contains images of breast cancer cells treated with a collection of 113 small molecules
at 8 different concentrations over 24 hours. It is housed in 55 zip archives, each approximately 850MB in size. Because of the size of the
dataset we will work on one zip archive first.

## Processing the Data
Each image in the archives corresponds to one quadrant and one of the RGB channels of one fully constructed well. This means before final
feature extraction, the images will need have their quadrants stitched together and their channels stacked. However, before channel stacking,
illumination filtering needs to be performed. In our case, a median filter needs to be applied to the images. This is a process whereby 
512px radius circles of the image are successively sampled and the centre pixel re-coloured to the median value of the sampled circle. NumPy
provides a library to perform this filtering, however attempting to use this method led to a memory error. This is apparently a known issue
for this function, and so a workaround was suggested by Juan using their own filtering function. Although this has the disadvantage of being
slower, it has the key advantage of being functional.

Once we change the illum code to use this alternative function, we will be able to stitch and stack the images, and perform feature extraction.
