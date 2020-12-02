# CEREC: Corpus for Entity Resolution in Email Conversations

Corpus containing 6001 Enron email threads weakly-annotated for entity coreference resolution task. The actual emails can be downloaded from [here](https://www.cs.cmu.edu/~./enron/).

More details are available in [our paper](https://www.aclweb.org/anthology/2020.coling-main.30.pdf) (which should be cited if you use or discuss CEREC in your work).

</p>
<div class="highlight highlight-source-shell"><pre>
@inproceedings{dakle-moldovan-2020-cerec,
    title = "{CEREC}: A Corpus for Entity Resolution in Email Conversations",
    author = "Dakle, Parag Pravin  and
      Moldovan, Dan",
    booktitle = "Proceedings of the 28th International Conference on Computational Linguistics",
    month = dec,
    year = "2020",
    address = "Barcelona, Spain (Online)",
    publisher = "International Committee on Computational Linguistics",
    url = "https://www.aclweb.org/anthology/2020.coling-main.30",
    pages = "339--349",
    abstract = "We present the first large scale corpus for entity resolution in email conversations (CEREC). The corpus consists of 6001 email threads from the Enron Email Corpus containing 36,448 email messages and 38,996 entity coreference chains. The annotation is carried out as a two-step process with minimal manual effort. Experiments are carried out for evaluating different features and performance of four baselines on the created corpus. For the task of mention identification and coreference resolution, a best performance of 54.1 F1 is reported, highlighting the room for improvement. An in-depth qualitative and quantitative error analysis is presented to understand the limitations of the baselines considered.",
}
</pre></div>

## Corpus Description

CEREC contains 6001 email threads from the Enron Email Corpus containing 36,448 emailmessages and 38,996 entity coreference chains.

An email thread annotation is saved in the CoNLL format with the following naming convention:

username_directory_email_no.conll

where:

username - Name of the user directory in the Enron Email Corpus.

directory - Name of the directory for the specific user.

email_no - Filename in the specific directory.

Each annotation file is an eight column tab separated file and contains speaker, entity type (P: PER, O: ORG, L: LOC, D: DIG) and coreference annotations. Detailed column information in the order found is as follows:

The columns contain:

Column | Type         | Description
:-----:|----------------|--------------------------------------------
1      | Token             | The actual token as found in the email thread
2      | MI             | The value of message identifier feature for the token
3      | SI           | The value of section identifier feature for the token
4      | Speaker           | The speaker of the token
5      | Entity Type        | The type of the entity this token represents. This column also contains two additional annotations - coreference chain informaion for the entity type encoded in a parenthesis structure and if the entity is the antecedent given by "*". E.g. In "(P0*", ( implies the token is starting a mention span, P implies the token is of PER entity type, 0 implies the token belongs to the coreference chain with id 0 for PER entity type, and * implies it is part of the antecedent of the coreference chain.
6      | Mention | Mention information encoded in a parenthesis structure.
7      | Coreference | Coreference chain information encoded in a parenthesis structure.

The corpus can be found in zip file in the following directory <pre>data/COLING/</pre>

The zip file contains the following files:
1. cerec.conll - The CEREC corpus containing 6001 email threads, and their mention and coreference annotations.
2. cerec.validation.XX.conll - Email threads used in the validation set for CEREC experiments. These email threads were also used as validation and test sets for feature evaluation.
3. mention.corrected.XX.conll - Email threads that were manually corrected for mention annotations and then used to train a model for annotation quality evaluation.
4. seed.conll - The email threads from the seed corpus containing feature annotations and separated mention annotations.

## Experiments

The code used to generate the results can be found [here](https://github.com/mandarjoshi90/coref). Evalution scripts for all metrics can be found [here](https://github.com/conll/reference-coreference-scorers).


# Seed Annotated Corpus for Entity Resolution in Email Conversations

Corpus containing 46 Enron email threads manually-annotated for entity coreference resolution task. The actual emails can be downloaded from [here](https://www.cs.cmu.edu/~./enron/).

More details are available in [our paper](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.8.pdf) (which should be cited if you use or discuss this corpus in your work).

</p>
<div class="highlight highlight-source-shell"><pre>
@inproceedings{dakle-etal-2020-study,
    title = "A Study on Entity Resolution for Email Conversations",
    author = "Dakle, Parag Pravin  and
      Desai, Takshak  and
      Moldovan, Dan",
    booktitle = "Proceedings of The 12th Language Resources and Evaluation Conference",
    month = may,
    year = "2020",
    address = "Marseille, France",
    publisher = "European Language Resources Association",
    url = "https://www.aclweb.org/anthology/2020.lrec-1.8",
    pages = "65--73",
    abstract = "This paper investigates the problem of entity resolution for email conversations and presents a seed annotated corpus of email threads labeled with entity coreference chains. Characteristics of email threads concerning reference resolution are first discussed, and then the creation of the corpus and annotation steps are explained. Finally, performance of the current state-of-the-art deep learning models on the seed corpus is evaluated and qualitative error analysis on the predictions obtained is presented.",
    language = "English",
    ISBN = "979-10-95546-34-4",
}
</pre></div>

## Corpus Description

The seed corpus contains 46 email threads comprising of 245 email messages. These threads are split into a 36:10 train:test split. The corpus can be found in the following directory <pre>data/LREC/</pre>

An email thread annotation is saved in the CoNLL format with the following naming convention:

username_email_no.conll

where:

username - Name of the user directory in the Enron Email Corpus.

email_no - Filename in the inbox folder of the specific user.

Each annotation file is a four column tab separated file and contains speaker, entity type (P: PER, O: ORG, L: LOC, D: DIG) and coreference annotations. Detailed column information in the order found is as follows:

The columns contain:

Column | Type         | Description
:-----:|----------------|--------------------------------------------
1      | Token             | The actual token as found in the email thread
2      | Speaker           | The speaker of the token
3      | Entity Type        | The type of the entity this token represents. This column also contains two additional annotations - coreference chain informaion for the entity type encoded in a parenthesis structure and if the entity is the antecedent given by "*". E.g. In "(P0*", ( implies the token is starting a mention span, P implies the token is of PER entity type, 0 implies the token belongs to the coreference chain with id 0 for PER entity type, and * implies it is part of the antecedent of the coreference chain.
4      | Coreference | Coreference chain information encoded in a parenthesis structure.

## Experiments

The code used to generate the results can be found [here](https://github.com/mandarjoshi90/coref). Evalution scripts for all metrics can be found [here](https://github.com/conll/reference-coreference-scorers).

[The code to convert predictions back to CoNLL format in the coref repository did not work for us. Our .jsonlines to .conll converter can be found in jsonlines2conll.py and can be run as follows:]: #

[python3 jsonlines2conll.py <jsonlines_filepath> <gold_conll_filepath> <output_filepath>]: #
    
[where
jsonlines_filepath: The path to the  predicted .jsonlines file which is to be converted back to a .conll file with the predicted coreference annotations.
gold_conll_filepath: The path to the gold .conll file which was used as an input for obtaining predictions.
output_filepath: The path to save the generated .conll filepath.]:#
