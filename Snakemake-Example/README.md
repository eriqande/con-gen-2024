# Setting things up to work with this example

Students at ConGen should not have to do these steps. These are instructions on how an individual user *would* set up their conda/mambda environments, but I am providing this here simply so that the course IT gurus like Ted can pre-install the necessary environment on a virtual machine image, so everyone has it.

This is what I did to set up the environment:

``` sh
# install mambaforge
wget "https://github.com/conda-forge/miniforge/releases/latest/download/Mambaforge-$(uname)-$(uname -m).sh"
bash Mambaforge-$(uname)-$(uname -m).sh

# agree to some things and confirm default locations...

# type "yes" to use conda init.

# then activate it by sourcing .bashrc
source ~/.bashrc


# after that we want to get snakemake and the other tools we will need
# for the tutorial.
# open the Snakemake-Example tarball and cd into the directory
gunzip Snakemake-Example.tar.gz 
tar -xvf Snakemake-Example.tar 
cd Snakemake-Example

# then tell mamba to create a snakemake-example environment
mamba env create --file env/snakemake-example.yml
```

That is all that is needed to install the environment.

Once it is done, it can be tested by doing:
```sh
# activate env
conda activate snakemake-example

# run snakemake. This should run without errors
snakemake -p --cores 2 results/vcf/all.vcf
```

This takes about a minute and a half.  

Each student should have a _clean_ and _fresh_ copy of the
directory Snakemake-Example in their home directories that
they can use for my snakemake tutorial.

Do not simply copy the Snakemake-Example directory you have been working
in---that has all sort of products from the workflow that we do not want there.
Rather, get a fresh copy of the directory as sent to you.

Thanks!

eric


