# Armenian MFA

In-progress project on forced alignment of Armenian using the [Montreal Forced Aligner](https://montreal-forced-aligner.readthedocs.io/). 

## What we did
We trained a new [model](/armenian_acoustic_model.zip) on the Armenian data from the [FLEURS dataset](https://huggingface.co/datasets/google/fleurs). The dataset is around 14 hours of Eastern Armenian speech. We normalized the transcriptions to remove word-internal and word-external punctuation. The normalization was manual because some word-internal punctuation can cause a difference in pronunciation. The `.txt` files in [text_textgrid](/text_textgrid/) are these normalized forms. 

We manually the pronunciation dictionary in [pronDict](/pronDictOriginal.txt) by examining the tokens in FLEURS against the Armenian Wiktionary entries on [Wikipron](https://github.com/CUNY-CL/wikipron/blob/master/data/scrape/tsv/hye_armn_e_narrow_filtered.tsv). The model generated a [dictionary](/pronDictFinal) with weights. The model generated the TextGrids in [text_textgrid](/text_textgrid/). These alignments seem accurate but not perfect. 

## What we will do
There was a number of out-of-vocabulary words that we are slowly adding to the pronunciation dictionary. These were numbers that were often pronounced differently by different speakers. We are also double-checking the individual sound files to find errors in the transcript. 

