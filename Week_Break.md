# Week Break

Things are finally coming together! We've got our script on the remote machine and it's almost ready to run! We've finalised the fixes by making sure all the tests pass, so the pull request is now merged.

## Script Editing
Our script required some minor tweaks to ensure it works with the multiple directory structure of the 55 archives. It simply meant writing a function which rather than iterating through one folder, walks an entire directory and its subdirectories, matching filenames using a basic regular expression. We discovered the naming conventions for the wells and plates was slightly confusing, so we have now prepended the directory name to the image filenames, to make sure we have a unique identifier for each one when it comes to stitching and stacking. It means we should be able to again just alphabetically sort to ge the right order for ```montage_stream()``` to simply run through all of the illumed files and montage them.

## Testing Fix
We've now managed to manually confirm that the illum values are correct using the SciKit filters. Unfortunately, we discovered another small bug in the process of doing so (about 4 hours into our script running illumination correction), meaning we will have to rerun that part of the script after we reinstall the fixed and merged microscopium. Luckily, we have also learned of the ```screen``` command, which allows us to keep working while the script runs in the background. Now there should be nothing standing in the way of us processing all of the archives into the bokeh app (except time), once we reinstall microscopium. Since we have some illumed photos (even though they're wrong) from the first run of the script, we will work to make sure montaging them works correctly, while the correct illumination runs. Hopefully this means we'll only need to run the montage code once.

## Finding Corrupted Files
While the illum script was running, we also made sure that any decompression errors did not result in missing files which would break the montaging. Although there were some errors, each archive contained only full sets of 12 for each well (4 quadrants x 3 channels), meaning we should have no missing data when montaging. Upon manual inspection of some of the directories we found about 9 have a different naming convention as well, so it's important we make sure our regexs still match those directories.
