# Configuration

Using ServiceX requires some configuraiton. Firstly, you must authenticate with the service as it provides access to an experiment's data. Second you need to configure your local environment to run the various tools.

## Getting an account

## Python modules

All the python modules can be pip-installed.

## Jupyter Installation

The `servicex` library uses progress indicators in Jupyter notebooks to let you know how the processing is going. For this to work properly this requires some extra packages and setup in Jupyter.

Once done you'll get graphical progress bars in Juypter-Lab and Notebook that look like this:

![Example of Jupyter-Lab Progress Bars](images/jupyter-lab-progress-bars.png)

Two lines appear for each dataset. The first line shows the progress at the ServiceX - how many files have been completed, how many total. The second line shows how many files have been downloaded locally.

Note: When the query is first submitted the system does not know the total number of files in the dataset, so a very large number appears. It will update as soon as ServiceX reports the actual number.

### Jupyter Lab Configuration

To get the nice graphic progress bars in Jupyter Lab do the following:

1. In jupyter-lab, select the extensions tab:
   ![Picture of clicking on extensions manager tab](images/jupyter-lab-extensions-manager.png)
1. Look for the extension called `jupyterlab-manager`. This contains all the in-line widgets. Click `Install`.

1. You'll have to wait while it first downloads the extension.

1. Click `rebuild` when it shows up at the top of the extensions pallet. The rebuild process can take a few minutes.

1. Click `Reload` when the option is available.

1. You are now ready to fetch data and get a nice set of graphical ants marching across the screen:



### Jupyter Notebook Configuration
