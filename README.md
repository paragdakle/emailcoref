# Seed Annotated Corpus for Entity Resolution in Email Conversations

Corpus containing 46 Enron email threads manually-annotated for entity coreference resolution task. The actual emails can be downloaded from [here](https://www.cs.cmu.edu/~./enron/).

More details are available in [our paper]() (which should be cited if you use or discuss this corpus in your work).

</p>
<div class="highlight highlight-source-shell"><pre>
@inproceedings{dakle2020study,
  title =     {A Study on Entity Resolution in Email Conversations},
  author =    {Dakle, Parag Pravin and Desai, Takshak and Moldovan, Dan},
  booktitle = {Proceedings of the Twelfth International Conference on Language Resources and Evaluation (LREC 2020)},
  year =      {2020},
  pages =     {to appear},
}
</pre></div>

## Corpus Description

The seed corpus contains 46 email threads comprising of 245 email messages.

An email thread annotation is saved with the following naming convention:

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
