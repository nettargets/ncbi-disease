# NCBI Disease Corpus

NCBI Disease corpus from [here](https://www.ncbi.nlm.nih.gov/CBBresearch/Dogan/DISEASE/)
This dataset is well known for a standard NER dataset for disease.

# Files

**train**

`original-data/train/NCBItrainset_corpus.txt`

**dev**

`original-data/devel/NCBIdevelopset_corpus.txt`

**test**

`original-data/test/NCBItestset_corpus.txt`

# Download

```
gsutil cp  gs://ntc-datasets/ncbi-disease/NCBItrainset_corpus.txt
```

```
gsutil cp  gs://ntc-datasets/ncbi-disease/NCBIdevelopset_corpus.txt
```

```
gsutil cp  gs://ntc-datasets/ncbi-disease/NCBItestset_corpus.txt
```

# Evaluation

You can evaluate NER model's output using `conlleval` perl script from [here](https://www.clips.uantwerpen.be/conll2000/chunking/conlleval.txt).

Run the following command:

```
./script/conlleval < data/sample.txt
```

# sample.txt

```
Boeing NNP B-NP B-NP
's POS B-NP B-NP
747 CD I-NP I-NP
jetliners NNS I-NP I-NP

Rockwell NNP B-NP B-NP
said VBD B-VP B-VP
the DT B-NP B-NP
agreement NN I-NP I-NP
```

The `conlleval` script is originally developed for evaluating BioCreative's chunking task, Here, in the sample, `NP` from the sample means `noun` and `VP` means `verb`. 'B-', 'I-' and 'O-' parts represent the 'beginning', 'inside', and 'outside'. Please refer to [here](https://en.wikipedia.org/wiki/Inside%E2%80%93outside%E2%80%93beginning_(tagging)) for more info

# Output

```
$ ./script/conlleval < data/sample.txt 
processed 8 tokens with 5 phrases; found: 5 phrases; correct: 5.
accuracy: 100.00%; precision: 100.00%; recall: 100.00%; FB1: 100.00
               NP: precision: 100.00%; recall: 100.00%; FB1: 100.00  4
               VP: precision: 100.00%; recall: 100.00%; FB1: 100.00  1
```
