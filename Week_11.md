# Week 11

This week was dedicated to analysing the performance of the algorithms as classifier, designing the poster, and making some small UI improvements ahead of the demonstrations.

## Performance Analysis
Now that we have our data embdedded, it's time to assess how well the relationships between MOAs have been maintained on the 2D scatterplot. This means we'll want to run some classifier on the data. Some options would be kNN, Decision Trees / Random Forests, and assessing the distances between replicate wells and other wells.
Ideally we will be able to get a decent accuracy in classification on all 3 algorithms, and will see little difference between sampling objects or assessing all of them. In theory, UMAP claims it performs better than tSNE in embedding, so it will be interesting to compare the two on this dataset, particularly since UMAP is so recently "on the market".
Some exploration will be required to see which of these methods is best, but kNN is a simple classifier with easy to interpret results and whose overarching theory makes a lot of sense for our data set - we posit that dots closer together are related more than dots further away.

## Poster Design
Since the poster presentations are imminent, we want to make sure that we have a very solid idea of what we want on the poster. Juan and Genevieve want very little text, which means our visual aids have to be very effective.
We also want to add a process diagram to the poster, and feature it relatively front and centre, which highlights what it takes to take a raw image set and see it on the Bokeh app. This will help take a lot of the text out of the poster, and will make it a lot easier to get a decent overview of what microscopium actually is. 
We also want a logo to tie microscopium to the galaxy of its namesake, and a couple of screenshots of the app itself, of course. We want to have the poster design completely finalised at Monday's meeting.

## UI Improvements
There are still some UI improvements to be made. namely colouring by MOA and giving the ability to switch between the different embedding systems. This means we had to tweak the data CSVs being output by our file processing script to include a group column, namely the MOA, and all the x, y columns for PCA, tSNE and UMAP. This means we can run the bokeh app with just one CSV and it still gives us the ability to see the performance of the different embeddings.

## LOTS OF WORK TO DO!
