# SPOT: Sentiment Polarity Annotations Dataset

The SPOT dataset contains 197 reviews originating from the Yelp'13 and IMDB collections ([1][2]),
annotated with segment-level polarity labels (positive/neutral/negative). Annotations 
have been gathered on 2 levels of granulatiry:

 - Sentences
 - Elementary Discourse Units (EDUs), i.e. sub-sentence clauses produced by a state-of-the-art
RST parser [3]

This dataset is intended to aid sentiment analysis research and, in particular, the evaluation 
of methods that attempt to predict sentiment on a fine-grained, segment-level basis.

Statistics and details about the dataset's creation can be found in our paper:

> **Multiple Instance Learning Networks for Fine-Grained Sentiment Analysis**,<br/>
> Stefanos Angelidis, Mirella Lapata. 2017. <br/>
> _To appear in Transactions of the Association for Computational Linguistics (TACL)_.<br/>
> [ [arXiv](https://arxiv.org/abs/1711.09645) ]

The models proposed in the paper are trained using _document-level supervision only_, on the 
**original** Yelp'13 and IMDB collections. Preprocessed versions of the 2 original datasets, 
including both sentence- and EDU-split variants, are available 
[**here**](https://drive.google.com/open?id=1T-6_BWax1l4diZy9-ksehHOC9S7FOqeN).

For questions or comments, please email `s.angelidis [at] ed.ac.uk`

If you use this dataset in your research, please cite the above paper.

### Details

The SPOT dataset is split into 4 subsets based on the origin (Yelp'13 / IMDB) and segmentation 
policy (sentences / EDUs) used, resulting in the following 4 files:
 - `spot-yelp13-sent.txt`
 - `spot-yelp13-edus.txt`
 - `spot-imdb-sent.txt`
 - `spot-imdb-edus.txt`

Each file lists documents and their fine-grained annotations using the following format:

1. A document begins with a line containing its document-level sentiment label (0 to 4 for 
Yelp'13, 0 to 9 for IMDB), followed by exactly 1 space character, and a document id, unique for 
the particular collection.
2. The individually annotated segments are listed after that, one segment per line. Each line
begins with a single character that indicates the segment-level sentiment label (+/0/-), 
followed by a single `<tab>`, and the segment itself.
3. After all the segments are listed, a single empty line marks the end of the document.

#### Example:
```
3 0318862
-	This location is in a scary neighborhood .
+	But , the inside was renovated with mcd 's new interior design .
+	So it looks nice and well kept up thus far .
-	The cashier i got tried to charge me for using my living social deal .
-	He said it was just $ 1 off , when in fact the ls deal was prepaid for already .
+	I told him to ask his manager and she would correct him , which she did .
+	Fries were good .
0	I likely will return to this location , but maybe not at night .
[ empty line ]
```

## References

[1] Duyu Tang, Bing Qin, and Ting Liu. 2015.
**Document modeling with gated recurrent neural network for sentiment classification.**
_In Proceedings of the 2015 Conference on Empirical Methods in Natural Language Processing, pages 1422–1432, Lisbon, Portugal._

[2] Qiming Diao, Minghui Qiu, Chao-Yuan Wu, Alexander J. Smola, Jing Jiang, and Chong Wang. 2014.
**Jointly modeling aspects, ratings and sentiments for movie recommendation (JMARS).**
_In Proceedings of the 20th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining, pages 193–202, New York, NY, USA._

[3] Wei Vanessa Feng and Graeme Hirst. 2012. 
**Text-level discourse parsing with rich linguistic features.**
_In Proceedings of the 50th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers), pages 60–68, Jeju Island, Korea._
