# GENERAL DESCRIPTION

This program analyzes large genotyping data. In particular it checks for mismatches in the data between child and mother.
The program is coded in *Java*, using the *Apache POI* for treating *Excel* (as well as *Calc*) files. Consider the input size to be *n* times *m*, with *n* the number of individuals, and *m* the number of locus'. The algorithm proceeds in a linear fashion, comparing siblings' genomes to the mother's genomes. It thus runs in optimal time *O(nm)*. Small improvements may be made to improve practical running time, but are not needed currently. Memory usage is bounded by *O(m)*.

This *README* contains two parts:

- the context in which this program was developed; 
- how to execute the program and read the results.

## GENOTYPING CONTEXT

*To be determined.*

## EXECUTION AND RESULTS

A specific file format is **mandatory** for the correctness of the results. This format is presented in *format.xlsx*, and two example data sets respecting this format are given in the *input* folder.

If this is the first time using this program, we recommend going through the **first time installations** below. 

Once everything is installed, the program may be executed as follows:
	
1. Put the *Excel* data file (respecting the format) in *input* folder.

2. Open terminal in *mismatchfinder* folder.

3. Enter:

	```
	sh mismatchfinder.sh
	```

(This will execute the program on **all** files in *input* folder.)

4. Wait until terminal prints: 

	```
	------------------    
	All files treated.    
	------------------
	```

5. Find results in the *output* folder. 

The results include:
+ Sheet *results*: for each mother, the number of mismatches is given.
+ Sheet *results_details*: for each mismatch, the mother and descendant with corresponding genotypes are given, as well as the locus and their position in the dataset.
+ Sheet *locus_mismatches*: for each mother and locus, the number of mismatches is given.
+ Sheet *heterozygous_children*: for each mother and locus, the number of heterozygous siblings is given.
+ Sheet *mismatches_vs_heterozygous*: For each mother and locus, the number of mismatches is compared to the number of heterozygous descendants. 

### FIRST TIME INSTALLATIONS

Start by downloading *mismatchfinder.zip* on https://github.com/jschoete/mismatchfinder and unzip it in the desired location. A copy of this *README* can be found inside.

**Java**

1. Open terminal.
	(For Windows users, press windows button and enter cmd.)

0. Check if Java is installed, by entering: 
	
	```
	java -version
	```

0. If Java is not installed, the terminal will print:

	```
	Java command not found
	```

0. In this case, install Java's latest version: https://docs.oracle.com/en/java/javase/index.html

**Cygwin** 
(for Windows users)

1. Install *Cygwin*: http://www.cygwin.com/

0. During setup, when prompted to select packages, search for **chere** package and replace *skip* with latest version.

0. Open *Cygwin* terminal (press Windows button and enter *Cygwin64 Terminal*) and enter: 
	
	```
	chere -i -t mintty -s bash
	```

0. Users can now open terminals in folders through the right click menu, with *Bash Prompt Here*.