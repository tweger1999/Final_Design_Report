### References
https://newscatcherapi.com/blog/ultimate-guide-to-text-similarity-with-python
https://huggingface.co/sentence-transformers/all-mpnet-base-v1
https://www.kaggle.com/datasets/littleotter/united-states-presidential-speeches?select=corpus.csv
### Code below: 
#### pres_speeches.py and seg_algorithm.py 
https://github.com/yahya010/DocClustering/Code
### Project Notes

10/14/2022 
Questions for Professor Minai:
What dataset to use? (20 newsgroup, US presidential speeches, Thinking Fast and Slow)
How many topics should we use? (are we using all 20 or a few or 1)
How do we get started with the embedding process? (What programs to use)
Using word, word pairs, and sentences and compare the three

Notes:
Origin of the species book. Make sure the source is legitimate (copyright reasons). Make sure it's long enough to get multiple topics.
Project Gutenberg
20 newsgroup is a good dataset, we have a topic label for each article
US presidential speeches is also a good dataset
Word level: can already be done
Sentence level: can already be done
Segment level: make segmentation algorithm
Embedding method, word embedding, use word to vec, glove, specifically encodes word, can also use BERT, does not recommend BERT though. One embedding for each word.
What is the best representation of that document using words?
Goal is to create a semantic space
Embed words and put them into semantic space for each document
Next level is to use sentences: split documents into sentences, for each sentence decide if it's worth including or not. Can either feed documents in continuously, resets or continues to embed sentences. (sentences one at a time or continuous flow). Each document will produce a large cloud semantic space, and can decide the most important sentences of that to extract summarization. Then cluster to get semantic space.
Same thing using segments of sentences
Start with sentence level.
Every document will produce a cloud of data points, build a semantic space where every document has a cloud of representation.
LDA?
Start with presidential speeches.
Mpnet for sentence embedding

-Use presidential speeches and embed sentences using npnet (look through other sentence embedding as well)
Follow Up Questions:
What is the difference between continuous flow and single sentence embedding?

Do we need to separate topics based on the date the speech was given? (how to handle different dialect and party shift)
embedding method, any changes?

10/21/2022
Classify where the president lies politically based on input values.
1st remove stop words, then remove a certain number of words.
Keep track of which president says what
Use PCA for dimension reduction
Validation mechanism: calculate pairwise between items in full space and in PCA 95 space. Take pairs in full space and PCA space and compare distances (cos distance) , make a plot of x and y distances and make a scatter plot. (should be sigmoid). Look at Omars thesis to compare. 
Randomly select subset of data points to calculate point distances between pairs of points
Map James Madison’s sentences into PCA-95 space and create vector map visualization
Calc pairwise distances between points
Take angular distance of points and 
Also try for more modern / other older presidents
Omit small sentences, this is just to check relationships.
Pairwise , cosine similarity, map angular distance. Map into 0,1 space (inverse cosine), output 
If mpnet doesn't work, look into other systems (USC)
Choose a book too. (origin of the species), project gutenberg, non fiction.
T-sne for mapping to 2 dimensions (only works on given dataset)
Remove stop words and short sentences.
Embed sentences - D
Run PCA 95
Calculate pair distances and compare
Using cosine similarity, map angular distance
Graph the comparison (bulk embedding vs PSA 95 embedding)
Ensure the graph is relative sigmoid and points correspond to each other
Run again for more recent president

11/04/2022
Question for Nov 4:
-What is the point of segmentation if we will cluster later on?
- next step? Filtering or validation (cos similarity) - > map into PCA95 before validation
- Does segmentation give us an idea about how good our embedding is?-why’s yahya a bitch??? I own u
Speech by speech works, combination gives two segments and doesn't look right, is this presidential speech wrong or something we are doing in the code wrong.
### Effort
We all worked together on implementing embedding algorithm as well as implementing the segmentation algorithm to group together sentences that are similar.
Research on the project and how to implement embedding, clustering and dimensionality reduction were based off of personal research as well as material and research papers provided by Dr. Ali Minai, adding up to 45 hours spent by each member on the project.

