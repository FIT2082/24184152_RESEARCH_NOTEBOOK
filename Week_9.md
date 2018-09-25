# Week 9

So as it turns out, sudo is a very fickle friend. Because we've only ever used Linux on our personal devices, we've never really run into the dangers of using sudo to install things on machines with multiple users and user groups. Although we successfully were able to install Anaconda into /mnt, using sudo to install it meant we ran into some issues. This week was dedicated to untangling the remote machine mess.

## Installing Anaconda
Because we installed Anaconda using sudo, it was difficult to give everyone permissions to use it in their own home directories. This meant we needed to wipe everything and start from scratch. With Juan's help we worked out the "standard practice" way to install Anaconda for multiple users to access is to install it in /mnt, provide one "base" or "default" environment to a group containing all the users, and then have each user derive their own environment from that. This means everyone is able to use the same distro and we save space compared to using multiple installs, but we also maintain the flexibility of each user having their own setup and packages, etc. 

## Installing Microscopium
Once Anaconda was set up, installing microscopium was easy. We were able to simply checkout the repository and install it (without using sudo) using pip, making the alpha channel fix manually, since both pull requests have yet to be merged. Now that we've finally managed to set up the remote machine environment, we can move our scripts over and get started. The first job will be making sure the code is generalised enough to work with the different archives. 

## Pull Request Testing
We got the clarification from Juan on what is required to ensure the tests are correct. Essentially there is one function performing the test which calculates the median filter of three small example images i, j and k and compares it to a manually calculated numpy array. We should be able to manually confirm a few of the output pixels before changing the manually declared "truth" value to match.
