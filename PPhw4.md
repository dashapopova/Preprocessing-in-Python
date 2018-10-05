## Homework 4 Assignment -- due 12.10 by 9:00

### Task 1: Initial Consonant Clusters \[10 points\]

Your task is to show me how to use pattern matching to investigate the distribution of
word-initial consonant clusters in *Alice* (alice.txt). The basic question is how frequent different
kinds of initial consonant clusters are. 

An initial consonant cluster is a sequence of consonants (not interrupted by vowels) at the beginning of a word.
E.g., *crouton* has an initial consonant cluster *cr*, *flamingo* has an initial consonant cluster *fl*, 
*mimosa* does not have an initial consonant cluster, it starts with a single consonant. 

A challenge here is that English orthography only indirectly reflects the phonology.
First, you must deal with silent letters. These include cases like *know* or *gnostic* where *k* and
*g* are silent. Another issue to wrestle with is that sometimes a single consonant
is written with several letters, e.g. [θ] as in *thimble* or [ʃ] as in *show*, etc. Finally,
there are cases where the same letter (sequence) has multiple pronunciations. For
example, *c* is pronounced [s] in *city*, but [k] in *coat*. Similarly, *ch* is pronounced [tʃ]
in *church*, but [k] in *chord*. Note that sometimes the difference is predictable, as in
the case of *c*, but sometimes it is not, as in the case of *ch*. You should set aside
the mapping of orthography to precise phonological forms, except insofar as you
need to decide what a cluster is.

You will need to do the following (or something which is analogous to the following):

1. apply the `gutenberg_file_wc(filename)` (HW3 Q1,2) and the `view_wc(d)` (HW3 Q3) functions to alice.txt -- up to 4 points;
2. try to search for (word) initial consonant clusters using regular expression(s) (Don't forget to `import re` at the beginning of your program) -- up to 2 points;
3. do the counts for all the clusters that you have identified -- 2 points; 
4. print the clusters with the counts -- 1 point;
5. the Jupiter notebook file, comments -- 1 point.
