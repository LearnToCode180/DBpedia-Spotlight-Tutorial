# DBpedia-Spotlight-Tutorial

In this [tutorial](https://www.youtube.com/watch?v=CihrjNlBWnc&t=21s) I'm gonna show you how to use the Spotlight tool from a [Docker Image](https://hub.docker.com/r/dbpedia/dbpedia-spotlight/) to link your data entities with the DBpedia knowledge base. And we will use for that CMD, as well as Python.

The second thing you'll find in my jupyter notebook is how to annotate a long text using this tool, because it doesn't work if the text you're working on is very long.

Finally in the last part of my code, I shared with you a method to get the offsets of the entities of a long text which have been linked to the entries of the DBpedia knowledge graph (notice that I just used KB and KG interchangeably, I find in this [article](https://arxiv.org/abs/2112.01989) that the main difference between those two terms is that a KB does not have to be graph-structured, so any KG is a KB and not any KB is a KG). In a small text, you'll not find any problem on that, but in a long one, you should do some tricks to successfully get your offsets, and that's what I'm gonne show you in this [YouTube Video]().

You'll find here some useful informations about the two fundementals concepts used in this [tutorial]().

## Entity Linking
Entity linking [[3]](https://www.cs.jhu.edu/~delip/entity_linking.pdf) is matching a textual entity mention, possibly identified by a named entity recognizer, to a KB entry, such as a Wikipedia page that is a canonical entry for that entity. An entity linking query is a request to link a textual entity mention in a given document to an entry in a KB. The system can either return a matching entry or NIL to indicate there is no matching entry.

And They define in the same article that there are 3 challenges to entity linking:

1. **Name Variations:** An entity often has multiple mention forms, including abbreviations, shortened forms, alternate spellings, and aliases. Entity linking must find an entry despite changes in the mention string.

2. **Entity Ambiguity:** A single mention can match multiple KB entries, as many entity names, like people and organizations, tend to be polysemous.

3. **Absence:** Processing large text collections virtually guarantees that many entities will not appear in the KB (NIL), even for large KBs.

## Spotlight

DBpedia Spotlight [[4]](https://www.dbpedia-spotlight.org/docs/spotlight.pdf), a system for automatically annotating text documents with DBpedia URIs (i.e. annotation of DBpedia resources mentioned in text). In the annotation task, the user provides text fragments (documents, paragraphs, sentences) and wishes to identify URIs for resources mentioned within that text. DBpedia Spotlight allows users also to configure the annotations to their specific needs through the DBpedia Ontology and quality measures such as prominence (how many times a resource is mentioned in Wikipedia), topical relevance (how close a paragraph is to a DBpedia resource’s context), contextual ambiguity (is there more than one candidate resource with similarly high topical relevance for this surface form in its current context?) and disambiguation confidence. And it can take full advantage of the DBpedia ontology for specifying which concepts should be annotated because annotations can be  restricted to instances of specific classes (or sets of classes) including subclasses. Alternatively, arbitrary SPARQL queries over the DBpedia knowledge base can be provided in order to determine the set of instances that should be annotated.