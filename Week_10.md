# Week 10
This week we finally got the pipeline completed and all photos in the 55 archives have been illumed, montaged and had their features extracted. Now we are ready to analyse the performance of the different clustering algorithms. We also submitted a WIP pull request to microscopium_scripts for the scripts which takes raw images and produces the CSV required for Bokeh.

## Racing Scripts
Upon initially running the feature extraction, it took roughly 90 seconds per image. With 2760 images, this was about 60 hours of processing. We started the script on Wednesday at 11:30am and it ended on Friday at ~9:30pm, so it did indeed take 60 hours to process.
While this feature extraction was running we performed feature extraction with a sample size of 100. This essentially means that 100 pixels at a time are sampled for percentile features, as opposed to an individual pixel. This sped up the process dramatically and took 533 minutes (just shy of 9 hours).
This is a massive increase in performance, so it'll be interesting to see the effect it has on the embeddings. If the difference is negligible, then this is a great way to speed up computation and make microscopium more usable overall.

## Illum Troubles
We noticed after montaging the images that some of them had clearly visible "seams" at the quadrant edges as a result of the illumination being overzealous. This was hypothesised by Juan to be a small proportion of the images, and still better than the majority of images lifted off microscopes. It will be interesting to note whether these "seams" are identified as "features" by the algorithms and lead to them being clustered together. If that is the case, then this is definitely a drawback to microscopium's usability.

## Scaling
Genevieve pointed out this week that our features were not normalised before dimension reduction. This is definitely likely to skew our results as the ranges of the different features are not equal. We will therefore use a standard scaler (literally, StandardScaler in Scikit Learn's preprocessing library) to standardise the features to zero mean and unit variance. Luckily this occurs after feature extraction, so we're not 60 hours behind again. Scaling will be the final step before clustering is used to assess microscopium's ability to cluster compounds and moa's.
