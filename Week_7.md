# Week 7

- figured out what was wrong with multiple images - alpha channel not accounted for, using microscopium image loading func now
- submitted pull requests for both the illumination filtering fix, and the multiple image loading fix 
- first ever pull requests!
- as part of submitting the pull requests, learned some new useful Git command line tools and gained a better understanding of what pull requests are and how we should handle the repositories
- inquired about how to "install" microscopium - turns out it's a pip package
- need to also make sure we are running off the anaconda distro to ensure all the dependencies are satisfied
- once microscopium is installed with pip we can then use it from anywhere 

- because the code takes some time (about 20 minutes start to finish) to run on one zip archive, and we have 55 of them, we will need to use a more powerful remote machine to process the full dataset, one because it's faster and two because it would take like 12 hours of our laptop being out of commission
- next job therefore is to set up anaconda and microscopium on the remote machine so that we can use the script we've written to process the full 38000 or so images!
