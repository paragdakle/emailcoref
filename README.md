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

The seed corpus contains 46 email threads comprising of 245 email messages. These threads are split into a 36:10 train:test split.

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
