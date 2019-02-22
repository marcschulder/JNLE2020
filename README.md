# Bootstrapped Creation of a Lexicon of Sentiment Polarity Shifters
This repository contains data due to be submitted as part of:

[Schulder, Marc](http://marc.schulder.info), [Wiegand, Michael](http://www.coli.uni-saarland.de/~miwieg/) and [Ruppenhofer, Josef](http://ruppenhofer.de/) (to be submitted). **"Bootstrapped Creation of a Lexicon of Sentiment Polarity Shifters"**.

## Content
We provide a bootstrapped lexicon of English polarity shifters and their shifting direction.
We cover verbs, nouns and adjectives.
Our lexicon provides 2521 shifters among a vocabulary of 9145 words, taken from WordNet v3.1 (Miller et al., 1990).

We also provide a dataset of 2631 verb phrases that are annotated for shifting polarities.
The phrases are taken from the Amazon Product Review Data corpus (Jindal & Liu, 2008).

### Related Resources
- **[IJCNLP 2017](https://github.com/uds-lsv/bootstrapped-lexicon-of-english-verbal-polarity-shifters):** Lexicon of English Verbal Shifters (bootstrapped, lemma-level)
- **[LREC 2018](https://github.com/uds-lsv/lexicon-of-english-verbal-polarity-shifters):** Lexicon of English Verbal Shifters (manual, sense-level)
- **[COLING 2018](https://github.com/uds-lsv/bootstrapped-lexicon-of-german-verbal-polarity-shifters):** Lexicon of German Verbal Shifters (bootstrapped, lemma-level)

## Data
### 1. Polarity Shifter Lexicon
A list of 9145 words, annotated for whether they are polarity shifters and which polarities they affect.
Contains 2631 shifters and 6514 non-shifters.

- File: `shifters.txt`
- The lexicon is a comma-separated value (CSV) table
- Each line follows the format `POS,LEMMA,SHIFTER_LABEL,DIRECTION_LABEL,SOURCE`.
  - `POS`: The part of speech of the word (`verb`, `noun`, `adj`)
  - `LEMMA`: The lemma representation of the word in question. Multiword expressions are separated by an underscore (`WORD_WORD`).
  - `SHIFTER_LABEL`: Whether the word is a polarity shifter (`SHIFTER`) or a non-shifter (`NONSHIFTER`)
  - `DIRECTION_LABEL`: Whether the shifter affects only positive polarities (`AFFECTS_POSITIVE`), only negative polarities (`AFFECTS_NEGATIVE`) or can shift in both directions (`AFFECTS_BOTH`). Non-shifters are all labeled (`NONE`).
  - `SOURCE`: Whether the word was part of the gold standard (`GOLD_STANDARD`) or was bootstrapped (`BOOTSTRAPPED`). Note that while bootstrapped shifter labels are verified by a human annotator, their direction label is automatically classified without verification.

### 2. Sentiment Verb Phrases
A set of verb phrases, annotated for the polarity of the verb phrase and the polarity of a polar noun that it contains.
Can be used to evaluate whether a polarity classifier correctly recognizes polarity shifting.
The file starts with 400 phrases containing shifter verbs, followed by 2231 phrases containing non-shifter verbs.

- File:  `sentiment_phrases.txt`
- Every item consists of:
  - The sentence from which the VP and the polar noun were extracted.
  - The VP, polar noun and the verb heading the VP.
  - Constituency parse for the VP.
  - Gold labels for VP and polar noun by a human annotator.
  - Predicted labels for VP and polar noun by RNTN tagger (Socher et al., 2013) and `LEX_gold` approach.
  - Items are separated by a line of asterisks (*)

## Attribution
This data set is published under [Creative Commons Attribution 4.0](https://github.com/uds-lsv/bootstrapped-lexicon-of-english-verbal-polarity-shifters/blob/master/LICENSE).

## Acknowledgements
This work was partially supported by the German Research Foundation (DFG) under grants RU 1873/2-1 and WI4204/2-1.

## References
G. Miller, R. Beckwith, C. Fellbaum, D. Gross, K. Miller: "Introduction to WordNet: An On-Line Lexical Database". International Journal of Lexicography, 3:235-244, 1990.

N. Jindal and B. Liu: "Opinion Spam and Analysis", in Proceedings of ACM-WSDM, 2008.

R. Socher, A. Perelygin, J. Wu, J. Chuang, C. Manning, A. Ng, C. Potts: "Recursive Deep Models for Semantic Compositionality Over a Sentiment Treebank", in EMNLP, 2013.
