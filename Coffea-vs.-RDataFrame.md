# Setup

## RDataFrame (Python)

To run the code using RDataFrame (RDF) you need ROOT > 6.22
You can do the following:

```
 cmsrel CMSSW_11_2_0_pre6_ROOT622
 cd src
 cmsenv
```

or:

```
 . /cvmfs/sft.cern.ch/lcg/app/releases/ROOT/6.22.02/x86_64-centos7-gcc48-opt/bin/thisroot.sh
```

With the latter you'll have warnings due to edm format information not available:
`Warning in <TClass::Init>: no dictionary for class ...`


## RDataFrame (C++)

Compile application including ROOT libraries:

```
g++ makeHistogramsRDF.cpp -o makeHistogramsRDF `root-config --cflags` `root-config --libs`
```

and then run with `./makeHistogramsRDF`


# Coffea

To run Coffea you can create a virtual environment (this will take time):

```
 source makeCoffeaEnv.sh
```

Or you can source Florian's virtual environment:

```
 source /afs/cern.ch/user/f/fleble/virtualEnv/coffeaenv/bin/activate
```


Once the virtual env is created you can simply run the script as usual:

```
 python makeHistogramsCoffea.py
```

At the end, you can deactivate the virtual env:

```
 deactivate
```

To activate the virtual env:

```
 source coffeaenv/bin/activate
```
