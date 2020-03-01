ReadMe:
Corpus for submission titled: A study on Entity Resolution in Email Conversations
Authors: 
- Parag Pravin Dakle (paragpravin.dakle@utdallas.edu)
- Takshak Desai (takshak.desai@utdallas.edu)
- Dan I. Moldovan (moldovan@utdallas.edu)

The seed corpus contains 46 email threads comprising of 245 email messages.

An email thread annotation is saved with the following naming convention:

<username>_<email_no>.conll

where:
username - Name of the user directory in the Enron Email Corpus.
email_no - Filename in the inbox folder of the specific user.

Each annotation file is a four column tab separated file and contains speaker, entity type (P: PER, O: ORG, L: LOC, D: DIG) and coreference annotations. Detailed column information in the order found is as follows:

Column  Type            Description
    1   Token           The actual token as found in the email thread
    2   Speaker         The speaker of the token
    3   Entity Type     The type of the entity this token represents. This column also contains two additional annotations - coreference chain informaion for the entity type encoded in a parenthesis structure and if the entity is the antecedent given by "*". E.g. In "(P0*", ( implies the token is starting a mention span, P implies the token is of PER entity type, 0 implies the token belongs to the coreference chain with id 0 for PER entity type, and * implies it is part of the antecedent of the coreference chain.
    4   Coreference     Coreference chain information encoded in a parenthesis structure.
