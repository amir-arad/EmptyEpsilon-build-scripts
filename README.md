# EmptyEpsilon-build-scripts

scripts to build EE releases
## setup
install latest [vagrant](https://www.vagrantup.com/) 
```
$ vagrant version
Installed Version: 2.2.0
Latest Version: 2.2.0

You're running an up-to-date version of Vagrant!
```
install .env file plugin
```
vagrant plugin install vagrant-env
```
maybe also need to install [virtualbox](https://www.virtualbox.org).

## execute
set environment variables `EMPTY_EPSILON` and `SERIOUS_PROTON` with absolute paths to git clones of respected libbraries, and set `RELEASE` to the destination folder, and run vagrant from the command line:
``` 
$ export EMPTY_EPSILON="/workspace/EmptyEpsilon" SERIOUS_PROTON="/workspace/SeriousProton" RELEASE="/workspace/release"; vagrant up --provision
```
alternatively, create a file named `.env` at the same folder of the vagrantfile, with the correct paths:
```
EMPTY_EPSILON="/workspace/EmptyEpsilon"
SERIOUS_PROTON="/workspace/SeriousProton"
RELEASE="/workspace/release"
```
and simply run 
```
$ vagrant up --provision
```

In my experience, not all builds work the first time, but sometimes a second run works. so if the result .zip file does not contain an `.exe` file, I suggest running `$ vagrant up --provision` again.

when you're done building, make sute to run 
```
$ vagrant halt
```
to stop the virtual machine, as it is not secured.

## cleanup

the virtual machine is saved in the local hard drive. so run 
```
$ vagrant destroy
```
when you want to free up space