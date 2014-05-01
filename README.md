python27 for centos6
====================

**Build your own python 2.7.x RPM for RHEL/Centos 6.x automatically with Vagrant**

After years of manually trying to build the latest python 2.7.x on Centos and never remembering how to do it, I decided to leverage Vagrant to automatically do it in one shot. Even [Centos SCL](http://wiki.centos.org/AdditionalResources/Repositories/SCL) which is supposed to house the latest and greatest is still a minor rev behind.

## Dependencies
* `Vagrant` (tested on v1.5.1 on Mac & Windows) 

## Instructions
* git clone this repo
* cd into it
* modify the PYVER variable at the top of the scripts/build_python file to the version that you want in "2.7.X" format. Currently defaulting to 2.7.6
* optionally modify the box file URL in the Vagrantfile
* then just "vagrant up" (sometimes I have had to "vagrant provision" afterwards because it doesn't take on the first go around)

You should see a slew of messages fly by and if all is successful, you should see a "PYTHON 2.7.X BUILD SUCCESSFUL" message and the resulting rpms copied to the rpms dir contained within this repo. Otherwise you'll see an error message if the build didn't exit cleanly.

## Notes
* None of this would have been possible without [Pingviini's](https://github.com/pingviini/rhel6-rpmbuild) repo which is where I got the python27 spec file from. Beers on me pingviini if you're ever in NYC.
* I am using a government (NREL) box file (64-bit Centos 6.5 2014-03-11) as the build host because I `trust` our government. You can browse their box collection at http://developer.nrel.gov/downloads/vagrant-boxes/ Otherwise feel free to use your own.
* Hopefully this saved you some time and headache

