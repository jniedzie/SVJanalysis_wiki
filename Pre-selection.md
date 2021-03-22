### Installation
You need to have Coffea installed in your Python setup. See here how to [create a Coffea virtual environment](https://github.com/jniedzie/SVJanalysis/wiki/Create-a-Coffea-virtual-environment).

### Running

```
usage: makePreSelection.py [-h] -i INPUTFILES -o OUTPUT -t
                           {PFnano102X,PFnano106X} [-c CHUNKSIZE]
                           [-m MAXCHUNKS] [-n NWORKERS]

optional arguments:
  -h, --help            show this help message and exit
  -i INPUTFILES, --inputFiles INPUTFILES
                        Input ROOT files to skim. Format: Comma separated list
                        of files or txt file with list of file (1 file name
                        per line)
  -o OUTPUT, --output OUTPUT
                        Output ROOT file
  -t {PFnano102X,PFnano106X}, --fileType {PFnano102X,PFnano106X}
                        Input file type, mandatory argument
  -c CHUNKSIZE, --chunksize CHUNKSIZE
                        Size of the data chunks (default=100000)
  -m MAXCHUNKS, --maxchunks MAXCHUNKS
                        Maximum number of chunks to process, no flag means no
                        maximum
  -n NWORKERS, --nworkers NWORKERS
                        Number of worker nodes (default=4)
```

You can find an example in `runMakePreSelection.sh`.

### Output
The output skimmed ROOT files have 2 trees:
* `Events`: standard NTuple events tree
* `Cuts`: a tree with one branch `Efficiency`, having only one leaf, representing pre-selection efficiencies