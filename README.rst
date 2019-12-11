This is is the **revcomp** pipeline from the `Sequana <https://sequana.readthedocs.org>`_ projet

:Overview: Simply reverse complement a bunch of fastq files
:Input: fastq files
:Output: their reverse complement counterpart
:Status: production
:Citation: Cokelaer et al, (2017), ‘Sequana’: a Set of Snakemake NGS pipelines, Journal of Open Source Software, 2(16), 352, JOSS DOI doi:10.21105/joss.00352


Installation
~~~~~~~~~~~~

You must install Sequana first::

    pip install sequana

Then, just install this package::

    pip install sequana_revcomp


Usage
~~~~~

::

    sequana_pipelines_revcomp --help
    sequana_pipelines_revcomp --input-directory DATAPATH 

This creates a directory with the pipeline and configuration file. You will then need 
to execute the pipeline::

    cd revcomp
    sh revcomp.sh  # for a local run

This launch a snakemake pipeline. If you are familiar with snakemake, you can 
retrieve the pipeline itself and its configuration files and then execute the pipeline yourself with specific parameters::

    snakemake -s revcomp.rules -c config.yaml --cores 4 --stats stats.txt

Or use `sequanix <https://sequana.readthedocs.io/en/master/sequanix.html>`_ interface.

Requirements
~~~~~~~~~~~~

This pipelines requires the following executable(s):

- seqtk


Details
~~~~~~~~~

This pipeline runs **seqtk** in parallel on the input fastq files.


Rules and configuration details
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Here is the `latest documented configuration file <https://raw.githubusercontent.com/sequana/sequana_revcomp/master/sequana_pipelines/revcomp/config.yaml>`_
to be used with the pipeline. Each rule used in the pipeline may have a section in the configuration file. 
