# final_project
Repository for storing files from the final Data Processing project

The purpose of this project is to find evidence of evolutionary pressure on the Akt1 protein.


Installation & setup
Software required to run the complete notebook:
- Biopython 1.85	pip install biopython
- peptides 0.3.4	pip install peptides
- CLUSTAL 2.1		conda install -c bioconda clustalw
- Numpy 2.2.6		pip install numpy
- HMMER 3.4		conda install -c bioconda hmmer


Additional notes:

- Cell 14 uses the motif attribute .weblogo which returns an incompatible .png file. The graphic interface should instead be used which is available here: https://weblogo.berkeley.edu/logo.cgi. The graphic interface output is stored as ./results/large_gap_manually_retrieved.png

- cmd3 (creating index files) and cmd4 (aligning sequences to database) in cell 15 expect an unzipped 1.85 GB Pfam protein domain database in ./data. To avoid errors since the large database and index files are not in the GitHub repository, if-else statements were added so that the cell automatically checks at each step whether the output file of the command exists and skips to the first cmd of which output does not exist. This includes all cmds so that the cell is skipped entirely if pfam_results.txt exists in ./results

- Cell 18 was designed to call fetchPfamMSA() from the ProDy library. However since ProDy has not been updated since long and requires Biopython 1.79 and Numpy 1.24, a try-except construction skips the cell, but show the idea of it anyway. Manually generated alternative output is available as ./data/consensus_matched_domains.fasta

- Cell 23 calls NCBIWWW.qblast() which takes about 4 min for this data, but allows skipping the cell if output file ./results/blast_results.xml exists.

- Cell 25 calls clustalw which takes about 30 sec for this data, but allows skipping the cell if output file ./alignments/blast_sequences.aln exists.




