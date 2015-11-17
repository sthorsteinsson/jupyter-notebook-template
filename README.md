# jupyter-notebook-template
This repository serves as a help to projects where multiple people write on the same notebook.

## Create a new notebook projet
This section describes the steps necessary to take in order to make a new notebook project

1. Copy the setup folder "notebook_files" into the git repository where you want your notebook.
2. Go to git repository of interest
3. Create a new notebook using following line

`jupyter notebook`

4. export condo environment to the folder "notebook_files". Make sure the desired environment is active! Please do not change name of output file. Place "environment.yml" in the folder "notebook_files". 

`source activate desired_environment`
`conda env export > path/to/notebook_folder/environment.yml`


In order to config the notebook for use please run:

./run_setup.sh
