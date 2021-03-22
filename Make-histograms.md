### Installation
You need to have Coffea installed in your Python setup. See here how to [create a Coffea virtual environment](https://github.com/jniedzie/SVJanalysis/wiki/Create-a-Coffea-virtual-environment).

### Input ROOT files
The input ROOT files from which to make histograms must/can have 2 trees:
* `Events`: standard NTuple events tree (mandatory!)
* `Cuts`: a tree with one branch `Efficiency`, having only one leaf, representing pre-selection efficiencies (optional)

### Running
Beside the input ROOT files, several files are needed for making histograms:
* a sample description file (example in `samples.json`) which defines the location and cross-section of the different samples.
* a binning file (example in `binning.json`) which defines the binning of the different variables

The variables to histogram are defined and computed in a Coffea processor in `processorHistogram.py`. An example is already implemented in class `Histogram1`.

```
usage: makeHistograms.py [-h] [-m {recreate,update}] -b BINNING -sd
                         SAMPLESDESCRIPTION -s SAMPLES -p PROCESSOR
                         [-o OUTPUTDIRECTORY] [-l LUMI]

optional arguments:
  -h, --help            show this help message and exit
  -m {recreate,update}, --mode {recreate,update}
                        Mode in which to open the output ROOT file. Choices:
                        recreate (default), update
  -b BINNING, --binning BINNING
                        json file describing binning of the histograms
  -sd SAMPLESDESCRIPTION, --samplesDescription SAMPLESDESCRIPTION
                        json file describing samples location
  -s SAMPLES, --samples SAMPLES
                        Comma separated list samples to pick up among the
                        samples described in the sample file
  -p PROCESSOR, --processor PROCESSOR
                        Coffea processor to be used, as defined in
                        processorHistogram.py
  -o OUTPUTDIRECTORY, --outputDirectory OUTPUTDIRECTORY
                        Path to the directory where to recreate/update ROOT
                        file (default=./)
  -l LUMI, --lumi LUMI  Total luminosity for normalization of the histograms
                        (default=59725 pb-1)
```

You can find an example in `runMakeHistograms.sh`.