Getting Started
###############

This document will show you how to install and run Scikit-ribo.

What is Scikit-ribo
-------------------

Scikit-ribo is an open-source software for accurate genome-wide A-site prediction and translation efficiency
inference from Riboseq and RNAseq data.

Source Code: https://github.com/hanfang/scikit-ribo

Introduction
------------

Scikit-ribo has two major modules:

- **Ribosome A-site location prediction** using random forest with recursive feature selection

- **Translation efficiency inference** using a codon-lvel generalized linear model with ridge penalty

A complete analysis with scikit-ribo has two major procedures:

- The data pre-processing step to prepare the ORFs, codons for a genome: ``scikit-ribo-build.py``

- The actual model training and fitting: ``scikit-ribo-run.py``

Detailed workflow
-----------------
.. image:: /images/methods.png
   :align: center
   :scale: 75%

Inputs
------
- The alignment of Riboseq reads (bam)
- Gene-level quantification of RNA-seq reads (from either Salmon or Kallisto)
- A gene annotation file (gtf)
- A reference genome for the model organism of interest (fasta)


Output
------
- Translation efficiency estimates for the genes
- Translation elongation rate for 61 sense codons
- Ribosome profile plots for each gene
- Diagnostic plots of the models


Cite
----

Fang et al, "Scikit-ribo: Accurate inference and robust modelling of translation dynamics at codon resolution" (Preprint coming up)

Contact
-------

Han Fang

Stony Brook University & Cold Spring Harbor Laboratory

Email: hanfang.cshl@gmail.comRequirement
###########

Environment
-----------

- Python3
- Linux
- Recommend setting up your environment with `Conda <https://conda.io/docs/index.html>`_

Dependencies
------------

- Command-line pacakges:

+----------------+------------+
| Python package | Version >= |
+================+============+
| bedtools       | 2.26.0     |
+----------------+------------+

- Python package:

+----------------+------------+
| Python package | Version >= |
+================+============+
| colorama       | 0.3.7      |
+----------------+------------+
| glmnet_py      |0.1.0b      |
+----------------+------------+
| gffutils       | 0.8.7.1    |
+----------------+------------+
| matplotlib     | 1.5.1      |
+----------------+------------+
| numpy          | 1.11.2     |
+----------------+------------+
| pandas         | 0.19.2     |
+----------------+------------+
| pybedtools     | 0.7.8      |
+----------------+------------+
| pyfiglet       | 0.7.5      |
+----------------+------------+
| pysam          | 0.9.1.4    |
+----------------+------------+
| scikit_learn   | 0.18       |
+----------------+------------+
| scipy          | 0.18.1     |
+----------------+------------+
| seaborn        | 0.7.0      |
+----------------+------------+
| termcolor      | 1.1.0      |
+----------------+------------+

Note: When using pip install scikit-ribo, all the following dependencies will be pulled and installed automatically.

Installation
############

Options
-------
There are three options to install Scikit-ribo.


1. Install Scikit-ribo with pip::

    pip install scikit-ribo

2. Install Scikit-ribo with conda/biocodon::

    Coming up

3. Compile from source::

    git clone https://github.com/hanfang/scikit-ribo.git
    cd scikit-ribo
    python setup.py install

Test whether the installation is successful
-------------------------------------------
Once the installation is successful, you should expect the below if you type::

    scikit-ribo-run.py

.. image:: /images/successful_installation.png
   :align: center
   :scale: 75%