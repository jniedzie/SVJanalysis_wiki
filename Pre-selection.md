### Installation
You need to have Coffea installed in your Python setup. See here how to [create a Coffea virtual environment](https://github.com/jniedzie/SVJanalysis/wiki/Create-a-Coffea-virtual-environment).

### Running

```
usage: makePreSelection.py [-h] -i INPUTFILES -o OUTPUT -t {PFNanoAOD_102X,PFNanoAOD_106X_v01,PFNanoAOD_106X_v02} -xsec GENCROSSSECTION -p PROCESSOR [-c CHUNKSIZE]
                           [-m MAXCHUNKS] [-n NWORKERS] [-debug]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUTFILES, --inputFiles INPUTFILES
                        Input ROOT files to skim. Format: Comma separated list of files or txt file with list of file (1 file name per line)
  -o OUTPUT, --output OUTPUT
                        Output ROOT file
  -t {PFNanoAOD_102X,PFNanoAOD_106X_v01,PFNanoAOD_106X_v02}, --fileType {PFNanoAOD_102X,PFNanoAOD_106X_v01,PFNanoAOD_106X_v02}
                        Input file type, mandatory argument
  -xsec GENCROSSSECTION, --genCrossSection GENCROSSSECTION
                        Sample cross section before pre-selection, mandatory argument
  -p PROCESSOR, --processor PROCESSOR
                        Coffea processor to be used, as defined in processorPreSelection.py
  -c CHUNKSIZE, --chunksize CHUNKSIZE
                        Size of the data chunks (default=100000)
  -m MAXCHUNKS, --maxchunks MAXCHUNKS
                        Maximum number of chunks to process, no flag means no maximum
  -n NWORKERS, --nworkers NWORKERS
                        Number of worker nodes (default=4)
  -debug, --debug       Debug mode
```

You can find an example in `runMakePreSelection.sh`.

### Output
The output skimmed ROOT files have 3 trees:
* `Events`: standard NTuple events tree
* `Cutflow`: number of events (sum of generator weights) after each cut
* `Metadata`: sample cross section at gen level (no cut), total cut efficiency, float encoding file origin