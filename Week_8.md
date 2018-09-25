# Week 8

This week has been dedicated to setting up the remote machine to work with microscopium and the BBBC021 dataset, and making sure that microscopium is properly installed and our scripts are kept separate from the source code.

## Remote Machine Storage
Upon trying to install anaconda in our home directories, which was the suggestion from Juan, we ran into an out of space issue. This was strange as the four drives were supposed to have 250GB between them. As it turns out, the root storage which houses our home directories only has 10GB shared, and is typically designed to store the operating system and whatever else is needed to boot the machine into a workable state. The "bulk" of the machine's storage lives on dev/vdb on an ephemeral disk, which ubuntu typically formats for access through /mnt (and did in our case as well). This storage is "ephemeral" because it gets destroyed if the machine is ever shut down. This means we must wipe all mention of Anaconda from the machine, and install it again in /mnt with access for everyone. 

Other weird things are also occurring on the machine. For example, James has access to Genevieve's conda installation, even though it's in her home directory (i.e. he is able to use the conda command), while my home directory does not recognise any mention of Anaconda. This might be because Genevieve gave everyone permission to access it when she installed, but it doesn't explain why I can't access it...

## Sudo Trouble
While trying to install microscopium using pip on my local machine, I ran into some trouble through my gratuitous use of sudo. Because I used sudo together with pip to install some pacakges and also microscopium, there is a disconnect between the interpreter which recognises microscopium and other packages, and the interpreter which runs anaconda and most of my python. This will require Juan's help to sort out. However, we were able to appropriately install microscopium on James' device, and so we've been able to tweak our script to work separate from the source code, ready to place on the machine once it is set up.

## Pull Request Issues
One of the pull requests has been merged now (yay!), but we still need to merge the second. The test suite is now failing as the illumination returns slightly different values. This means we must manually change the test for ```find_background_illumination()``` to make sure the illumination values match. We are not sure exactly how to manually calculate the median filter, so we will need Juan's assistance on this. Once we get this done we'll have both fixes in one place which will make it a lot easier to install on the machine as well.
