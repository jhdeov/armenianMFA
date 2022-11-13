# Armenian MFA

In-progress project on forced alignment of Armenian using the [Montreal Forced Aligner](https://montreal-forced-aligner.readthedocs.io/). 

We trained an [acoustic model](/acoustic_model.zip) on the Armenian data from the [FLEURS dataset](https://huggingface.co/datasets/google/fleurs). The dataset is around 14 hours of Eastern Armenian speech. We normalized the transcript for the following:
* to remove word-internal punctuation
* to remove word-external punctuation
* to convert digits into number lemmas
* to find errors in the transcripts

We manually created a pronunciation dictionary by examining the tokens in FLEURS against the Armenian Wiktionary entries on [Wikipron](https://github.com/CUNY-CL/wikipron/blob/master/data/scrape/tsv/hye_armn_e_narrow_filtered.tsv).

The model generated [TextGrids](/generated_textgrids/) with word-alignment and phone-alignment. I currently have a bug that's preventing 56 files from getting aligned.


