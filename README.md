# EmptyEpsilon-build-scripts

scripts to build EE releases
## setup
install latest vagrant 
```
$ vagrant version
Installed Version: 2.2.0
Latest Version: 2.2.0

You're running an up-to-date version of Vagrant!
```
maybe also need to install virtualbox.

## execute
set environment variables `EMPTY_EPSILON` and `SERIOUS_PROTON` with absolute paths to git clones of respected libbraries and run vagrant from the 
``` 
$ export EMPTY_EPSILON="/media/amir/Windows/workspace2/EmptyEpsilon" SERIOUS_PROTON="/media/amir/Windows/workspace2/SeriousProton"; vagrant up --provision
```
when you're done building, make sute to run 
```
$ vagrant halt
```
to stop the virtual machine, as it is not secured.