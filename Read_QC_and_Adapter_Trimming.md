# 2) Read QC and Adapter Trimming

### Log onto UCSB VPN (Ivanti Secure Access Client)

#### Open Terminal on Macbook  

#### Log into braid2 via `ssh`  
    ssh username@braid2.cnsi.ucsb.edu 

### Install mamba in your home directory
    
####  Move into your home directory using the `cd` command
    cd ~

#### Download the latest version of the Miniforge3 installer using the `wget` command
	wget "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"

#### Run the interactive installer using the `bash` command, answering any questions as needed
    bash Miniforge3-$(uname)-$(uname -m).sh
    
    Make sure to have the installer add the mamba activation to your .bashrc file

#### Re-source your .bashrc file to activate mamba using the `source` command
	source ~/.bashrc
	
	There should now be a parenthetical enclosing the word "base" on the left hand side of the command prompt


### Install FastQC and Trimmomatic using mamba

#### Create a new mamba environment
    mamba create -n readQC -c bioconda trimmomatic
    
    Answer Y to the question about wanting to install the package and its dependencies

#### Activate mamba environment and install fastqc
	mamba activate readQC
	mamba install -c bioconda fastqc
	
	Test installation of both programs by bringing up the help menu:
	
	trimmommatic
	fastqc -h

#### Build job submission script to run fastQC on the fastq files

