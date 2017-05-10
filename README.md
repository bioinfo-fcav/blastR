# blastR
A fork of BlastR: A tool for searching and clustering RNA

BlastR is a new method for searching Non-Coding RNAs in databases. The strategy we adopted relies on the use of the mutual information embedded in di-nucleotides. We have shown that this approach has better sensitivity and specifity than other softwares with comparable computational cost. BlastR package is a perl wrapper for BlastP and it is part of the T-Coffee distribution. 

The BlastR paper is:
BlastR--fast and accurate database searches for non-coding RNAs. Bussotti G, Raineri E, Erb I, Zytnicki M, Wilm A, Beaudoing E, Bucher P, Notredame C. Nucleic Acids Res. 2011 May 30

Homepage of the original implementation: http://www.tcoffee.org/Projects/blastr/

This fork replaces the NCBI blastp search engine by DIAMOND, which is faster than NCBI and has great sensitivity.
