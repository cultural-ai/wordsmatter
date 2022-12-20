[![DOI](https://zenodo.org/badge/567786032.svg)](https://zenodo.org/badge/latestdoi/567786032)
# A knowledge graph of contentious terminology
An RDF knowledge graph of contentious terms from the cultural sector is based on the publication ["Words Matter"](https://www.tropenmuseum.nl/en/about-tropenmuseum/words-matter-publication) published by the Dutch National Museum of World Cultures.

"Words Matter" provides English and Dutch glossaries of problematic terms often found in museum databases. These glossaries include terms "that are sensitive to particular groups, that can cause offense, that elide important context, and that are understood as derogatory" (as it is explained in the publication).

In [the knowledge graph](https://github.com/cultural-ai/wordsmatter/blob/main/glossary.ttl), 75 English and 83 Dutch contentious terms are linked to explanantions on their usage and suggested alternatives from domain experts. For example, using a SPARQL-query, one could answer "What is an appropriate alternative for the term 'Slave' (when it is used to describe people in slavery in the cultural heritage context)?".

The Jupyter notebook [competency_questions.ipynb](https://github.com/cultural-ai/wordsmatter/blob/main/competency_questions.ipynb) demonstrates what kind of information it is possible to retrive from the knowledge graph.

The knowledge graph [concept scheme](https://github.com/cultural-ai/wordsmatter/blob/main/schema.ttl) with 3 custom classes and 6 custom properties is presented below on the diagram:

![The knowledge graph concept scheme](https://github.com/cultural-ai/wordsmatter/blob/main/wm_kg_schema.png)

The developed knowledge graph has been given persistent W3id.org URIs, documented according to FAIR practices (the documentaion properties are included in the .ttl files), and made openly available for reuse with the license [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

To access the knowledge graph, use [](https://w3id.org/culco/wordsmatter/). The concept scheme is available at [](http://w3id.org/culco#)
