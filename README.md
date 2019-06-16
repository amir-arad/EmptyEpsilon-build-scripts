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
maybe also need to install virtualbox.

## execute
set environment variables `EMPTY_EPSILON` and `SERIOUS_PROTON` with absolute paths to git clones of respected libbraries and run vagrant from the 
``` 
$ export EMPTY_EPSILON="/workspace/EmptyEpsilon" SERIOUS_PROTON="/workspace/SeriousProton"; vagrant up --provision
```
alternatively, create a file named `.env` at the same folder of the vagrantfile, with the correct paths:
```
EMPTY_EPSILON="/workspace/EmptyEpsilon"
SERIOUS_PROTON="/workspace/SeriousProton"
```
and simply run 
```
$ vagrant up --provision
```

when you're done building, make sute to run 
```
$ vagrant halt
```
to stop the virtual machine, as it is not secured.

## cleanup

the virtual machine is stateful. so be sure to run 
```
$ vagrant destroy
```
when done building
