An Experimental Study of the Learnability of Congestion Control
======================

This repository contains materials to reproduce the results of a 
[paper](http://web.mit.edu/keithw/www/Learnability-SIGCOMM2014.pdf), 
appearing at ACM SIGCOMM 2014, 
which explores the "learnability" of congestion control protocols
through the use of an automated protocol design tool, 
[Remy](http://web.mit.edu/remy/).

Prerequisites
================

You will need a C++11 compiler, git, and [protobuf-2.4.1](https://protobuf.googlecode.com/files/protobuf-2.4.1.tar.gz).

Steps
================

1. Get the [base ns-2 tarball](http://web.mit.edu/anirudh/www/ns-allinone-2.35.tar.gz) and untar it.

    ```
    tar zxvf ns-allinone-2.35.tar.gz 
    ```

2.  cd into the untarred folder 

    ```
    cd ns-allinone-2.35 
    ```
3.  Get rid of the original version of ns-2.35 alone (we leave the other auxiliary components as is).

    ```
    rm -rf ns-2.35 
    ```

4.  Clone our modified ns-2.35 repository

    ```
    git clone https://github.com/hbatmit/ns2.35 ns-2.35
    ```

5.  Check out the appropriate commit (represented by the SHA-1 hash in the README file for each folder)

    ```
    git checkout <SHA-1-hash>
    ```

    where <SHA-1-hash> is the commit ID mentioned in each figure. 

6.  Now install ns-2.35 with all its components

    ```
    ./install 
    ```

7.  cd into the folder that has the simulation scripts

    ```
    cd ns-2.35/tcl/ex/decomposability/congctrl/sim_scripts
    ```

8. Run the appropriate Python script to generate a Makefile for that experiment.
The Makefile has one target for each distinct ns-2 run required for that
experiment. Running with make -j N -k limits the number of parallel simulation
runs to N and "-k" allows the simulations to continue even if a few simulations
fail for some reason.

9. Next, run the appropriate analysis script to summarize the results.
