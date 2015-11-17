# jupyter-notebook-template
This repository serves as a help to projects where multiple people write on the same notebook.

In order to use this repository you need to install the following software in the given order
1. Get conda. follow the link, download and install according to guide.

http://conda.pydata.org/docs/download.html

2. get jupyter using conda

http://jupyter.readthedocs.org/en/latest/install.html

## Manuel Setup
This setup describes the steps to manually configuring the pre-commit fitler to the notebooks in a repository. The filters strip the output from the notebooks to avoid merge conflicts.

1. clone the repos "sthorsteinsson/jupyter-notebook-template" onto your computer. This repostitory contains all the files you need.

`git clone https://github.com/sthorsteinsson/jupyter-notebook-template.git `

2. Goto the repository where you want to apply the filter.

`cd path/to/git_repos`

3. copy the file "nbstripout.py" into the repository. This is the filter which strips the output from a .ipynb file.

4. Next we want to configure git to run the filter on commits. This is done by adding the following lines to the local config file found in:

`.git/config`

`git config --local filter.nbstripout.clean absolute/path/to/nbstripout.py`

`git config --local filter.nbstripout.smudge cat`

`git config --local filter.nbstripout.required true`

The first line points to the filter which is activated during commit. The second line can be used to reintroduce the output when pulling from remote repos. The last line ensures that the filter is always applied.

5. The following step informs that only .ipynb files should go through the filter. copy the file "attributes" into the folder ".git/info/"

6. The last step is to add the hook. A hook is called upon a certain event. In this case when we commit a notebook. copy the file pre-commit into the folder ".git/hooks/". The "pre-commit" file in ".git/hooks/" runs every time a commit is made.

## Automatized method (Not finished)

## Create a new notebook project
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
