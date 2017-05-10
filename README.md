# blastR
A fork of BlastR: A tool for searching and clustering RNA

BlastR is a new method for searching Non-Coding RNAs in databases. The strategy we adopted relies on the use of the mutual information embedded in di-nucleotides. We have shown that this approach has better sensitivity and specifity than other softwares with comparable computational cost. BlastR package is a perl wrapper for BlastP and it is part of the T-Coffee distribution. 

The BlastR paper is:
BlastR--fast and accurate database searches for non-coding RNAs. Bussotti G, Raineri E, Erb I, Zytnicki M, Wilm A, Beaudoing E, Bucher P, Notredame C. Nucleic Acids Res. 2011 May 30

Homepage of the original implementation: http://www.tcoffee.org/Projects/blastr/

This fork replaces the NCBI blastp search engine by DIAMOND, which is faster than NCBI and has great sensitivity.

NAME

	dmnd_blastR.pl - It runs DIAMOND blastp using the BLOSUMR scoring matrix

SYNOPSIS

	dmnd_blastR.pl database queryFile [DIAMOND blastp options][-pg]

DESCRIPTION

	* DIAMOND blastR takes a nucleotidic FASTA file as query input.
	* It converts it into a dinucleotidic sequences.
	* It calls DIAMOND blastp on it using the BLOSUMR as scoring matrix.

OPTIONS

	* Use the usual DIAMOND blastp parameters (for instance "dmnd_blastR.pl database queryFile W=7 mformat=2").
	* DIAMOND BlastR uses as default --gapopen=10 --gapextension=10 --threads=2.

NAME

	dmnd_formatdbR.pl - create databases for DIAMOND from one or more input nucleotidic files in FASTA format

SYNOPSIS

	dmnd_formatdbR.pl [formatdb options]

DESCRIPTION

	* It takes as input one (or more) nuleotidic multi FASTA files.
	* It converts it (them) into a dinucleotidic sequences apending the reverse complement of the input.
	* It creates an DIAMOND formatted database running makedb on the dinucleotidic database.

OPTIONS

	* Use the usual DIAMOND makedb parameters (for instance "dmnd_formatdbR.pl --in inputDatabase --db outDatabaseName")
	* By default dmnd_formatdb assumes that diamond makedb program name on your computer is just "diamond makedb". If this is not the case you must provide the field -pg with the diamond makedb path.

