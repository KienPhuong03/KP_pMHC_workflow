# KP_pMHC_workflow
Pipeline requirements
The example data contain information of all PSMs (peptide spectrum matches) detected from one run. We would like to process the data to concatenate the “Precursor abundance” of PSMs that are of the same sequence and summarize the PSM table. You can treat a peptide with oxidation as modification to be the same peptide sequence. Below are some requirements for the processing pipeline

Be able to do two types of filtering: 1) Filter the PSMs based on “Percolator q-Value”<0.05 or 2) Filter the PSMs based on “Percolator q-Value”<0.05, “Xcorr”>2, “Spectral Angle”>0.6 and report how many PSMs and also unique peptides meet the chosen filtering criteria
After filtering, concatenate the PSMs into unique peptides, sum all the “precursor abundance” from the same peptide sequence to be the abundance of this peptide. Some PSMs might not have a value for precursor abundance, so the function should be able to report how many PSMs are missing precursor abundance, what peptides don’t have abundance values at all (none of the PSMs corresponding to this peptide have precursor abundance), and what peptides has precursor abundance but some PSMs have empty values
Take the concatenated table as input, which has unique peptides in each row, and rank the peptides by precursor abundance 
Plot output
The following statistics and plots should be shown:
Show the distribution of “Delta M in ppm”, “Xcorr”, “Spectral Angle” in histograms after filtering the PSM table (step 1 above)
Show the ratio of PSMs with non-empty precursor abundance in a staggered barplot (number of PSMs without NA vs. number of total PSMs) or piechart. Similarly, show ratio peptides with non-empty precursor abundance in a staggered barplot or piechart
Show the histogram of precursor abundance distribution from the concatenated table (step 2 above)
Show top 15 peptides with highest precursor abundance and plot as the precursor abundance as bar graph 
Perform pathway enrichment on all filtered peptides and plot terms with adjusted p values<0.05 (see Enrichr)
