# jupyter-notebook-template
This repository serves as a help to projects where multiple people write on the same notebook.

In order to use this repository you need to install the following software in the given order
1. Get conda. follow the link, download and install according to guide.

http://conda.pydata.org/docs/download.html

2. get jupyter using conda

http://jupyter.readthedocs.org/en/latest/install.html

## Create a new notebook projet
This section describes the steps necessary to take in order to make a new notebook project

1. Copy the setup folder "notebook\_files" into the git repository where you want your notebook e.g. "notebook\_example.ipynb".
2. Go to git repository of interest.
3. Create a new notebook using following code line. Create new notebook and rename.

`jupyter notebook`

4. export condo environment to the folder "notebook\_files". Make sure the desired environment is active! Please do not change name of output file. Place "environment.yml" in the folder "notebook\_files". 

`source activate desired_environment`

`conda env export > path/to/notebook_folder/environment.yml`

5. add, commit and push the notebook and folder "notebook\_files"

`git add notebook_files/*`
`git add notebook_example.ipynb`
`git commit -m "new notebook released"`
`git push`

`conda env export > path/to/notebook_folder/environment.yml`

## Get a notebook

1. Clone repository containing notebook
2. Go into the folder "notebook\_files"
3. Run the file "run\_setup.sh". This will configure the folder to strip outputs from the notebook.

`./run_setup.sh`
