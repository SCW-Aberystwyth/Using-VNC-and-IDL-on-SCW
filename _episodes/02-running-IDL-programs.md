---
title: "Running IDL programs"
teaching: 10
exercises: 0
questions:
- "How do we run IDL programs on the command line?"
objectives:
- "Launch the IDL command line interface on a login node."
- "Launch the IDL command line interface on a compute node."
keypoints:
- "IDL must be loaded through a module"
- "We should run computationally intensive things on a compute node, not a login node."
- "Where possible we should wrap things into batch jobs that can run without user intervention."
---

# Loading software modules

As there can be multiple versions of software installed on SCW a system of loadable modules let you choose which version to have. IDL versions 8.4 and 8.7 are both installed. Version 8.4 is a copy licensed to Aberystwyth and can only be run by certain Aberystwyth users. 8.7 is licensed to SCW and anybody can use it. 

## Listing available modules

~~~
module avail
~~~
{: .bash}

or 

~~~
module av
~~~
{: .bash}

This will produce a long list of available software modules.

IDL is found in the `/apps/local/modules/languages` section near the bottom of this list.

~~~
----------------------------------------------------------------------------------- /apps/local/modules/languages ------------------------------------------------------------------------------------
anaconda/2019.03       IDL/8.7                java/13                matlab/R2019b          perl/5.30.0            python/3.7.2-gnu-4.8.5
IDL/8.4                java/11                matlab/R2019a          octave/5.1.0           python/2.7.16-gnu-8.1  python/3.7.2-gnu-8.1
~~~

## Loading the module

We can load the default version (8.7) of IDL by running:

~~~
module load IDL
~~~
{: .bash}

Or we can explicitly specify a version by doing:

~~~
module load IDL/8.7
~~~
{: .bash}


## Seeing which modules are loaded

The module list command shows which modules are loaded:

~~~
$ module list
Currently Loaded Modulefiles:
  1) null      2) IDL/8.7
~~~
{: .bash}

## Unloading modules

A single module can be unloaded with the `module unload` command or all modules can be unloaded with the `module purge` command.

~~~
$ module unload IDL
$ module list
Currently Loaded Modulefiles:
  1) null
~~~
{: .bash}

# Running IDL

The standard command line version of IDL can be launched with the `idl` command (after loading the module).

~~~
$ module load IDL
$ idl
IDL 8.7.2 (linux x86_64 m64).
(c) 2019, Harris Geospatial Solutions, Inc.

Licensed for use by: University of Swansea
License: MNT-5515312
IDL> 
~~~
{: .bash}

This has only launched on the login node and this should only be used for very quick and simple testing. 

Now lets allocate a node using the `salloc` command. 

~~~
$ salloc -n1 -t 0:10:0 --partition=development
salloc: Granted job allocation 188375
salloc: Waiting for resource configuration
salloc: Nodes scs0121 are ready for job
$ ssh scs0121
Last login: Fri Mar 29 11:18:51 2019 from sl1
[a.abc1@scs0121 ~]$ module load IDL
[a.abc1@scs0121 ~]$ idl
IDL 8.7.2 (linux x86_64 m64).
(c) 2019, Harris Geospatial Solutions, Inc.

Licensed for use by: University of Swansea
License: MNT-5515312
IDL> 
.
.
Do some work here
.
.
IDL> exit

[a.abc1@scs0121 ~]$ exit
logout
Connection to scs0121 closed.
$ exit
exit
salloc: Relinquishing job allocation 188375
$ 
~~~
{: .bash}



