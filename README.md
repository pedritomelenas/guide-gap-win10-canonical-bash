# guide-gap-win10-canonical-bash
Guide to install `gap` on a windows 10 machine with canonical bash


Install gmp `apt-get install libgmp-dev`

Install make `apt-get install make`

Download and unpack gap source from gap-system.org and enter the directory

Configure gap to be compiled with system gmp `./configure --with-gmp=system` and then make

## Packages

These are the special packages that need extra configuration, the rest will work without problems

### Normalizinterfaze

`apt-get install git cmake libboost-all-dev` (may be that last one can be simplified...) and follow the instructions in README.md

### Browse

`apt-get install libncurses5-dev libncursesw5-dev`

### Float

Installed cxsc (download from the repository given in README and compiled)

```
sudo apt-get install libmpc-dev libmpfi-dev libfplll-dev

./configure --with-cxsc=/usr/local/cxsc
```

Then

```
gap> LoadPackage("float");
#W dlopen() error: libcxsc.so.2: cannot open shared object file: No such file or directory
Error, module '/home/pedro/lib/gap4r8/pkg/float-0.7.4/bin/x86_64-pc-linux-gnu-gcc-default64/float.so' not found in
  if not LOAD_DYN( arg[1], false )  then
    Error( "no support for dynamic loading" );
fi; at /home/pedro/lib/gap4r8/lib/files.gd:579 called from
LoadDynamicModule( f ); at /home/pedro/lib/gap4r8/pkg/float-0.7.4/init.g:43 called from
<function "unknown">( <arguments> )
 called from read-eval loop at line 45 of /home/pedro/lib/gap4r8/pkg/float-0.7.4/init.g
Error, was not in any namespace called from
LEAVE_NAMESPACE(  ); at /home/pedro/lib/gap4r8/lib/package.gi:1212 called from
ReadPackage( pkgname, "init.g" ); at /home/pedro/lib/gap4r8/lib/package.gi:1585 called from
<function "LoadPackage">( <arguments> )
 called from read-eval loop at line 1 of *stdin*
you can 'quit;' to quit to outer loop, or
you can 'return;' to continue
brk>
```

If we choose `./configure --without-cxsc`, then it works

### xgap

`sudo apt-get install xorg libx11-dev libxaw7-dev`

Then configure and make

Important: move xgap-* folder to xgap

You need export DISPLAY=:0.0 and Xming or similar

### Singular

If you want to use `singular` package in `gap`, then you will need to install `Singular`

Follow the instructions for ubuntu given in the singular web page


### Failed

[ "carat", "linboxing", "pargap" ]
Install gmp `apt-get install libgmp-dev`

Install make `apt-get install make`

Download and unpack gap source from gap-system.org and enter the directory

Configure gap to be compiled with system gmp `./configure --with-gmp=system` and then make

## Packages

These are the special packages that need extra configuration, the rest will work without problems

### Normalizinterfaze

`apt-get install git cmake libboost-all-dev` (may be that last one can be simplified...) and follow the instructions in README.md

### Browse

`apt-get install libncurses5-dev libncursesw5-dev`

### Float

Installed cxsc (download from the repository given in README and compiled)

```
sudo apt-get install libmpc-dev libmpfi-dev libfplll-dev

./configure --with-cxsc=/usr/local/cxsc
```

Then

```
gap> LoadPackage("float");
#W dlopen() error: libcxsc.so.2: cannot open shared object file: No such file or directory
Error, module '/home/pedro/lib/gap4r8/pkg/float-0.7.4/bin/x86_64-pc-linux-gnu-gcc-default64/float.so' not found in
  if not LOAD_DYN( arg[1], false )  then
    Error( "no support for dynamic loading" );
fi; at /home/pedro/lib/gap4r8/lib/files.gd:579 called from
LoadDynamicModule( f ); at /home/pedro/lib/gap4r8/pkg/float-0.7.4/init.g:43 called from
<function "unknown">( <arguments> )
 called from read-eval loop at line 45 of /home/pedro/lib/gap4r8/pkg/float-0.7.4/init.g
Error, was not in any namespace called from
LEAVE_NAMESPACE(  ); at /home/pedro/lib/gap4r8/lib/package.gi:1212 called from
ReadPackage( pkgname, "init.g" ); at /home/pedro/lib/gap4r8/lib/package.gi:1585 called from
<function "LoadPackage">( <arguments> )
 called from read-eval loop at line 1 of *stdin*
you can 'quit;' to quit to outer loop, or
you can 'return;' to continue
brk>
```

If we choose `./configure --without-cxsc`, then it works

### xgap

`sudo apt-get install xorg libx11-dev libxaw7-dev`

Then configure and make

Important: move xgap-* folder to xgap

You need export DISPLAY=:0.0 and Xming or similar

### Singular

If you want to use `singular` package in `gap`, then you will need to install `Singular`

Follow the instructions for ubuntu given in the singular web page


### Failed

[ "carat", "linboxing", "pargap" ]
