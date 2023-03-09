# SOD1_SNP_finder
Program to find the SOD1:c.118G>A polymorphism from Sanger chromatograms in case of indel heterozygosity as described in Kountourantzis et al

1) GENERAL INFORMATION

The script is a Python code developed in-house to address a problem with genotyping a specific deletion (ENSCAFG00000008859:g.26540247del) that results in double peaks in heterozygous samples. These double peaks make it difficult to determine the genotype of the SNP of interest. To solve this problem, we developed a script that uses IUPAC degenerate nucleotide codes to represent double peaks and resolves them using an algorithmic approach. Here's how it works: The user inputs nucleotide reads from the chromatogram, and in cases where there's a double peak, the degenerate nucleotide code is used (W for an A/T double peak, S for a C/G double peak, etc.). Assuming that the chromatograms from the two DNA strands have shifted leftward due to the heterozygous deletion, the script resolves the nucleotides by comparing the codes between the current and preceding positions. For example, if R (G or A) is provided at a given position with A at the preceding position, the script deduces that A is at the given position. While there are instances where the script cannot resolve the nucleotide code (e.g., repeated K codes), it was able to accurately determine the genotypic class of a given sample (A/A, G/G, or G/A) in the case of the SNP in question. However, in the case of the SNP in question, we were able to resolve the genotypic class of a given sample (A/A, G/G, or G/A), whereby heterozygosity was deduced when the nucleotide code at the SNP position was, for example, A with the preceding code K (G or T).

2) HOW TO RUN

The script requires Python to be pre-installed on your computer. To run the script, locate and double-click the "SOD_SNP_finder_rev_v.1.2.py" file in the "SOD_SNP_finder_rev_v.1.2" folder.

Once you have opened the script, you will be prompted to input your sequence data into the respective cell. If you encounter a double peak in the chromatogram, you should use the corresponding IUPAC code for degenerate nucleotides (e.g., 'W' for an 'A/T' double peak). After inputting your sequence, press the "Find SNP" button.

The program is designed to correct for a single deletion between the two strands of DNA and infer the actual nucleotide sequence. If the outcome is unresolved, the program will use the corresponding degenerate code. In cases where the nucleotide is 'N', a heterozygous nucleotide can be assumed.

Please note that the program has been tested to run appropriately on both Windows and MAC operating systems. If you have any issues running the program or questions about its functionality, please refer to the user manual or contact technical support.
