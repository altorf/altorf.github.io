Introduction
The size of the peptidome sequence space, or the total of all possible combinations of  a peptide of N aminoacids is huge.  In order to estimate the size of the entire peptidome search space in relation to the total of potential MHCI peptides in the human genome we created a custom total translation of the human genome into octapeptides. To get a better grip on exploration of this human octapeptidome space, or all the genomic encoded octapeptides  we performed an in silico translation for the reference human genome GRCh38. Hypothetically all of these octapeptides can be transcribed and translated as the recent discoveries in the field of of non-canonical translation drastically increased the amount of potential peptides being expressed and discovered in  the MHCI peptidome. These cryptic MHC I-associated peptides (MAPs) are produced via two mechanisms: translation of protein-coding genes in non-canonical reading frames and translation of allegedly non-coding sequences.1

Most sequences in sequence space presumably have no function, leaving relatively small regions that are populated by naturally occurring genes. However the absence of a function may also be an interesting feature if the presumably functionless peptide encoded in the genome is expressed under upset or unusual conditions and sufficiently high enough to processed in the immune system.

A typical estimate of the size of entire peptidome sequence space is 20100 (approx. 10130) for a protein of 100 amino acids in which any of the normally occurring 20 amino acids can be found. 2
Since MHCI  is restricting our search to a defined length for peptides to 8 amino acids we will limit our calculations to peptides of 8 aa or simply 24 Nucleotides. For simplicity we also ignore post translational modifications and only assume the 20 amino acids used in normal translation.  The total number of possible peptides for this octapeptidome is 208 = 25.600.000.000 peptides. This number of 25.6 billion Octopetides is referred to a the total octapeptidome.   For the human Genome we have determined the total number of possible peptides by using the latest  update; GRCh38.p14, 3634521541 unique octaptptides are generated  bij insilico translation of all possible reading frames and strands.  


Material and methods
.  For GRCh38 the number of "attempted" octapeptide translations per DNA sequence is calculated as following:
length of sequence - (8 codons * 3 bp/codon) + 1
Formula 1

For example, 26nt DNA sequence = 26 - (24) + 1 = 3 * 8aa peptides



Results
There are 639 sequences given in GRCh38. Calculating with the above formula for each gives 3272074508 theoretical octapeptide sequences. (this is for one strand, how many unique are  there for both strands)?

Actual generated: 3272074508
Unique sequences generated: 1955004643
Unique "peptides" (sequences matching only 20aa + Selenocysteine): 1241124045
1241124045 / 3272074508 ~= 0.379 ~= 37% coverage of maximum possible coverage
1241124045 / 25600000000 ~= 0.048 ~= 4.84% coverage of all possible sequences
Total peptides: 2031284512
Other sequences (mismatches): 713880598  ?  
Checksum: 713880598 + 1241124045 = 1955004643, so all accounted for this time!

The most frequent peptide was KKKKKKKK with 275208. Here is the rest of the top 10:
247819 FFFFFFFF
226200 CVCVCVCV
214321 VCVCVCVC
209882 HTHTHTHT
209332 PPKVLGLQ
206504 THTHTHTH
200434 LPKCWDYR
192285 CNPSTLGG
186281 ASQSAGIT

 
Figuur 1 histogram with total number of possible peptides. the first large bin was deleted,

“To explain the 713880598, let me quickly explain the process. I open each sequence, translate the first 24bp using Biopython's translate function, record the result, then increment the position in the sequence by one. That means I also record those with stop codons or ambiguous translations. I also count them, which given the way I'm doing it also means sorting them alphabetically. After sorting and counting, I separate them by doing a search that allows only for the 21 amino acids. These are the "matches".””
 Here are the first 10 matches (alphabetically):
AAAAAAAA 4697
AAAAAAAC 37
AAAAAAAD 71
AAAAAAAE 153
AAAAAAAF 45
AAAAAAAG 521
AAAAAAAH 30
AAAAAAAI 52
AAAAAAAK 56
AAAAAAAL 169


“If I count the number of these unique "matches" I get 1241124045. All others are "mismatches". Here are the first 10 (alphabetically):””
******** 16802
*******A 133
******A* 6
*****A** 1
***A**** 1
**A***** 6
*A****** 8
A******* 48
******AA 4
*****A*A 1



“The * is the symbol for any stop codon. (If we wanted to, we could distinguish between stop codons.) So there were 16802 cases found of 8 consecutive stop codons. If I found the total number of unique mismatches I get 713880598.””

Previously, this was roughly the same step in the process where I discovered some sequences had gone missing. Now, if I count the number of unique sequences before separating them, I get 1955004643. Since 1241124045 + 713880598 = 1955004643, they're all accounted for this time!
Side note: I've searched and Selenocysteine doesn't appear anywhere, even though I allowed for it. So in this sense we can keep regarding the space as 20^8 instead of 21^8. However, this does emphasize that not all amino acids are created equally! I'm now curious to know what the distribution of amino acids is in these results.

![binning all 100](https://user-images.githubusercontent.com/123867206/222919767-d091ad4d-cbf7-4e7b-97ed-1cfafb93480d.png)


 2nd attempt 4 stran translation Original: 1241326723
Reverse: 1145394148
Complement: 1145640779
Reverse Complement: 1241600785
Original+Reverse: 2181900734
Complement+Reverse Complement: 2182485600
All 4: 3634521541

References
1.	Laumont, C. M. & Perreault, C. Exploiting non-canonical translation to identify new targets for T cell-based cancer immunotherapy. Cell. Mol. Life Sci. 75, 607–621 (2018).
2.	Dryden, D. T. F., Thomson, A. R. & White, J. H. How much of protein sequence space has been explored by life on Earth? J. R. Soc. Interface 5, 953–956 (2008).

