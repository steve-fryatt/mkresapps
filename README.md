MkResApps
=========

Add structured application links to Apps.


Introduction
------------

MkResApps is a small BASIC utility that creates a Relocatable Module to add links to files, directories and applications to the ResourceFS. The utility works from the command line, producing the required module from a source text file.

It is more flexible than the RISC& OS 3.5+ AddApp utility in that it can handle nested directories; it also pre-assembles the module so that the time to execute your !Boot sequence is minimised. MkResApps can also handle links to directories and files on your hard disc.


Building
--------

MkResApps consists of a collection of ARM assembler and un-tokenised BASIC, which must be assembled using the [SFTools build environment](https://github.com/steve-fryatt). It will be necessary to have suitable Linux system with a working installation of the [GCCSDK](http://www.riscos.info/index.php/GCCSDK) to be able to make use of this.

With a suitable build environment set up, making MkResApps is a matter of running

	make

from the root folder of the project. This will build everything from source, and assemble a working MkResApps module and its associated files within the build folder. If you have access to this folder from RISC OS (either via HostFS, LanManFS, NFS, Sunfish or similar), it will be possible to run it directly once built.

To clean out all of the build files, use

	make clean

To make a release version and package it into Zip files for distribution, use

	make release

This will clean the project and re-build it all, then create a distribution archive (no source), source archive and RiscPkg package in the folder within which the project folder is located. By default the output of `git describe` is used to version the build, but a specific version can be applied by setting the `VERSION` variable -- for example

	make release VERSION=1.23


Licence
-------

MkResApps is licensed under the EUPL, Version 1.2 only (the "Licence"); you may not use this work except in compliance with the Licence.

You may obtain a copy of the Licence at <http://joinup.ec.europa.eu/software/page/eupl>.

Unless required by applicable law or agreed to in writing, software distributed under the Licence is distributed on an "**as is**"; basis, **without warranties or conditions of any kind**, either express or implied.

See the Licence for the specific language governing permissions and limitations under the Licence.