# Week 7

This week's focus was merging the two fixes to microscopium - using the SciKit image rankfilters and the recently fixed multiple image loading, into the master branch. This means we submitted our first ever pull requests and learned a bit more about the structure of microscopium and its intended use.

## Multiple Image Loading Fix
As it turns out, the function performing the multiple image loading was making a call to an io function which did not account for the possibility of images not having alpha channels. This meant that our numpy arrays were thrown out of sequence, with some values being incorrectly interpreted as transparency values. The fix was easy enough and simply meant making a call to microscopium's own io function, which handles the possibility of an image not having an alpha channel. The test images already had alpha channels in the raw copies, and so they were not affected by this bug.

## Pull Requests
We now had two fixes to microscopium which needed to be merged into the master copy to make sure it was functional. This meant submitting a pull request, which we had never done before. The basic process was forking the microscopium repository, and making two different branches, one for each fix. This then allowed us to submit two different pull requests to microscopium, which Juan could merge in once he was satisfied that they were indeed correct. Since we had accidentally pushed the two fixes as one commit, this required a bit of Git-Fu which was very interesting to get a look at - I'll definitely need to Google if I need to do it again though...

## Microscopium Structure
After inquiring we've learned that microscopium should be installed and used as a pip package. This means we should be able to simply
- checkout the repository
- install it using ```pip install --no-deps --upgrade -e .``` (assuming we are in the top level directory of the source code)
Additionally, we also need to make sure that our code is running with the Anaconda Python interpreter, as that's the best way to ensure all the many dependencies are satisfied.
This means our next task before working on the full dataset is to properly install microscopium and separate our scripts from the source code.

## Nectar Remote Machine
Currently, running the code on one of 55 zip archives takes about 20 minutes from start to finish. This means we will need a machine which both has more RAM, and won't put one of our laptops out of commission for the roughly 18 hours of processing (not to mention all the times it undoubtedly crashes out and we have to start again...). Juan has set up a Nectar instance for us to use as a remote machine, which we can SSH into as required. 
This means we also need to set up anaconda and microscopium on the machine, so that we can use the script we've written to process the full 38,000 or so images! The script will require a bit of tweaking, but since user input has been kept to a minimum, it should not be too much hassle.
