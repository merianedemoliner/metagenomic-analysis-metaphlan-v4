# What is this repository?

This is a new version of the work done in [my personal repository](https://github.com/merianedemoliner/metaphlan-metagenomic-analysis) using [metaphlan library](https://github.com/biobakery/MetaPhlAn). This time I'm using the metaphlan version 4 to process my data.

## Installation steps

<strong>Operational System</strong>: Ubuntu Linux, vUbuntu 20.04.4 LTS, 64-bit

The installation is entirely done using Termianl from linux.

I have followed MetaPhlAn instructions to set the MetaPhlAn channel in conda, [here](https://github.com/biobakery/MetaPhlAn/wiki/MetaPhlAn-4#pre-requisites). So for this version I'm just creating a new environment to get the updated versions for its pre-requisites.

Let's confirm I have the bioconda channel installed on my conda:
  
```conda config --get channels``` 

The return confirmed that among the defaults I already had bioconda AND conda-forge in place. The conda-forge was also suggested by the MetaPhlAn documentation and was probably installed in during my previous work.

Now, I need a specific conda environment which I named as mpaV4: 

```conda create --name mpaV4 -c bioconda python=3.7 metaphlan```

During the installation conda asked to update several packages which I have agreed via in the terminal.

Then I needed to download the database and clade markers which requires ~15GB, make sure you have this much available in your hard disk. It is advised to do that outside of the folders of your conda environment, BUT still in your conda enviroment. So, you should have your conda environment activated and when installing the database place it in folder that's not the one from the metaphlan library. In short, keep following the commands I'm suggesting, will keep describind what is happening, I hope you can benefit from it :)

Let's jump in my just created environment by typing:  
```conda activate mpaV4```  

Now, let's install the database in specific folder. I choose one closer to where I'm creating this repository. You could place where you develop your stuffs or in specific database folder closer to the $HOME folder. For this documentation I'm using `~/Documents/dev/db/metaphlan_databases`. Feel free to choose by your own, but keep in mind that you will need the path for the database folder when running the commands or consuming from this repository.
  
```metaphlan --install --bowtie2db ~/Documents/dev/db/metaphlan_databases```

  