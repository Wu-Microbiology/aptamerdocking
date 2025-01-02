# aptamerdocking
This repository includes the implementation of "Elucidating the Molecular Docking and Binding Dynamics of Aptamers with Spike Proteins Across SARS-CoV-2 Variants of Concern. 

The code works by comparing every sequence in the file with each other and if two sequences are similar enough (similarity threshold is provided by the user), they are placed in the same cluster. The program will save that cluster if there are more than the specified amount (provided by the user) of sequences in that cluster. If the similarity threshold is less than 1, clusters are then analyzed and the most common sequence in the cluster is set as the “representative
sequence” for the cluster. If you are searching for sequences within a certain length, the code first filters out all sequences that are not within the length threshold window. It then takes each sequence and does a pairwise alignment with the last ~10 bases of the NGSfoward_2 primer extension (not including the regular SELEX primer portion) and the first ~10 bases of the NGSreverse_2 primer extension (again, not including the regular SELEX primer portion). Based on this pairwise alignment, the program then truncates the sequence where it thinks the NGS primer extensions
are to hopefully achieve sequences without the NGS primer extensions that are 80bp long (only the 40bp random sequences and 20bp SELEX primers on either side). It then filters out all truncated sequences that are less than 70bp long and uses these ~80bp sequences as the new “representative sequences”.

If prompted, “representative sequences” from different clusters are compared with each other to see if they are reverse complements of each other. If they are and if prompted, the clusters are merged with each other.

Please cite our paper if you use our codes or models. The repository is still actively under development, please let us know if you encounter and issues.
