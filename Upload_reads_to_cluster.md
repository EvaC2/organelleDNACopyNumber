# 1) Upload reads to cluster using Secure Copy Protocol (SCP)

### Log onto UCSB VPN (Ivanti Secure Access Client)

#### Open Terminal on Macbook  

#### Use `cd` command to move into the proper directory  
    cd /path/to/directory/containing/files  

#### Log into braid2 via `ssh`  
    ssh username@braid2.cnsi.ucsb.edu 
    
    You will be prompted to enter a password  

#### Move to the scratch directory  
    cd /scratch  

#### If a directory for you does not already exist, create one  
    mkdir username  

#### Move into your directory  
    cd username  

#### Create a project directory  
    mkdir <projectName>  

#### Move into newly created project directory, and obtain the pathway using the `pwd` command  
    cd projectName  
    pwd  

#### Open a new terminal tab using Ctl + t  

#### Use the `scp` command to upload your fastq files to braid2 in the project directory you just created  
    scp -r <folder_containing_fastq_files> username@braid2.cnsi.ucsb.edu:/pathway/to/project/folder/  

#### Once transfer is complete, use the `ls -l` command to check whether file sizes are the same
    On the tab logged into Braid2:  
        ls -l projectName/*
    
    Compare the output to the same command on your local machine:
        ls -l folder_containing_fastq_files/*
    
#### If file sizes are the same, then you have successfully uploaded files to the cluster using the `scp` command
