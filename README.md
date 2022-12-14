# Armenian MFA

In-progress project on forced alignment of Armenian using the [Montreal Forced Aligner](https://montreal-forced-aligner.readthedocs.io/). 

We trained an [acoustic model](/acoustic_model.zip) on the Armenian data from the [FLEURS dataset](https://huggingface.co/datasets/google/fleurs). The dataset is around 14 hours of Eastern Armenian speech (n=4380 sound files). We normalized the transcript for the following:
* to remove word-internal punctuation
* to remove word-external punctuation
* to convert digits into number lemmas
* to find errors in the transcripts

We manually created a pronunciation dictionary by examining the tokens in FLEURS against the Armenian Wiktionary entries on [Wikipron](https://github.com/CUNY-CL/wikipron/blob/master/data/scrape/tsv/hye_armn_e_narrow_filtered.tsv).

We at first trained the model with a beam of 100. The model generated TextGrids for [4324 sound files](/generated_textgrids/v1_beam_100/) with word-alignment and phone-alignment. We then re-ran the model on the data with a beam of 1000 to get TextGrids for [4379 sound files](/generated_textgrids/v1_beam_1000/). One file seems to be broken. 

Each TextGrid has the following structure:
* `words` tier, generated by MFA.
* `phones` tier, generated by MFA.
* `sentenceOriginal` tier, manually generated. Lists the original transcript from FLEURS.
* `sentenceNormalized` tier, manually generated. Lists the transcript that we created by normalizing the `sentenceOriginal` tier. The model was run over this tier.
* `notes` tier, manually generated.




