# Week 12

The end is near! We've managed to do a boatload of work this week which led to a really neat poster with some great performance stats! It turns out microscopium has a pretty fantastic classifying ability, and we'll be able to do even more work for the report to show this.

## Performance
Microscopium with tSNE embedding sampling over all objects of an image led to an average classification accuracy of ~76%, with a sd of just 0.01848, for the best value of K tried in KNN classification. UMAP performed more poorly in both all objects, and sampled objects feature extraction, although the two algorithms were both quite capable in classifying. More interestingly, the classification accuracy was robust for all three algorithms across both sampling methods for all values of K.
This is actually a new research result! (According to Juan). 
Nobody has yet proven that any of the high dimension feature space relationships can be maintained at the 2D level for images of this nature i.e. we are the first to show you can perform classification just based on the 2D coordinates of the embedded points. This is very neat!

## Poster Design
This was my proudest visual design tool, because I suck at design and James did all of it. But I was still very proud. The poster looked very well designed and tidy, and the text wasn't too small yay! I was very happy with how well we were able to tell the microscopium story without ending up with a research paper in A0 format. The process diagram was 15/10 - again James' painstaking work.
We ended up including three very powerful indicators of our performance on the poster - the decision boundary plot which shows the number of sampled points which ended up in the right bucket, a confusion matrix which shows just how good 76% is, and shows no biased misclassification, and the plot of the distribution of accuracy among the different values of K. This not only made or poster vibrant and colourful, but meant it was very easy for us to use it as a reference piece, and explain exactly what was going on.
People actually tried our demo and seemed genuinely interested so yay!

## UI Improvements
We also added the ability into microscopium to live switch between the three embedding algorithms. This is awesome because not only does it turn the power of exploration up to 11, but it also means we can take advantage of what the different algorithms are best at. For example, even though PCA was kind of a trashy classifier, it was very good at pulling out the fluffy images.

## Report
For the report, we'll keep analysing performance of microscopium against other measures, such as a decision tree, a KNN on the full feature space, and other such metrics. Overall, we're really happy with our work for microscopium, and how much we've learned this semester. Getting a research result out of it is just the cherry on top!
