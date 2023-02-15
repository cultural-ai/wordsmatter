[![DOI](https://zenodo.org/badge/567786032.svg)](https://zenodo.org/badge/latestdoi/567786032)
# A knowledge graph of contentious terminology
An RDF knowledge graph of contentious terms from the cultural sector is based on the publication ["Words Matter"](https://www.tropenmuseum.nl/en/about-tropenmuseum/words-matter-publication) published by the Dutch National Museum of World Cultures.

"Words Matter" provides English and Dutch glossaries of problematic terms often found in museum databases. These glossaries include terms "that are sensitive to particular groups, that can cause offense, that elide important context, and that are understood as derogatory" (as it is explained in the publication). We call such terms "contentious".

In [the knowledge graph](https://github.com/cultural-ai/wordsmatter/blob/main/glossary.ttl), 75 English and 83 Dutch contentious terms are linked to explanantions on their usage and suggested alternatives from domain experts. For example, using a SPARQL-query, one could answer "What is an appropriate alternative for the term 'Slave' (when it is used to describe people in slavery in the cultural heritage context)?".

The Jupyter notebook [competency_questions.ipynb](https://github.com/cultural-ai/wordsmatter/blob/main/competency_questions.ipynb) demonstrates what kind of information it is possible to retrive from the knowledge graph.

The knowledge graph [concept scheme](https://github.com/cultural-ai/wordsmatter/blob/main/schema.ttl) with 2 custom classes and 6 custom properties is presented below on the diagram:

![The knowledge graph concept scheme](https://github.com/cultural-ai/wordsmatter/blob/main/wm_kg_schema.png)

The developed knowledge graph has been given persistent W3id.org URIs, documented according to FAIR practices (the documentaion properties are included in the .ttl files), and made openly available for reuse with the license [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).
The HTML-version of the scheme documentation was generated using [WIDOCO](https://zenodo.org/badge/latestdoi/11427075):
"java -jar java-11-widoco-1.4.17-jar-with-dependencies.jar -ontFile schema.ttl -uniteSections -ignoreIndividuals -noPlaceHolderText -getOntologyMetadata -htaccess -rewriteAll -outFolder docs".

To access the knowledge graph, use https://w3id.org/culco/wordsmatter/. The concept scheme is available at http://w3id.org/culco#

We have also made the knowledge graph available on [TriplyDB](https://triplydb.com/AndreiNesterov/Words-Matter-LOD/)

### Related matches

The knowledge graph has URIs of contentious labels, which we link to four LOD-resources: controlled vocabularies used by cultural heritage institutions (Wereldculturen Thesaurus (NMVW) and Getty AAT) and commonly used LOD-resources (Wikidata and Princeton WordNet 3.1).
NMVW is a thesaurus of the Dutch National Museum of World Cultures, which published the original glossaries.

###### The process of identifying related matches:

1. Collecting a list of query terms for every contentious label:
-	[getting_word_forms.ipynb](https://github.com/cultural-ai/wordsmatter/blob/main/getting_word_forms.ipynb): collecting word forms for every contentious label from [DBnary](http://kaiko.getalp.org/about-dbnary/) (for English terms) and [INT](https://ivdnt.org/corpora-lexica/corpora/#corpus-compilation) (for Dutch terms)
-	[wordforms_added_manually.json](https://github.com/cultural-ai/wordsmatter/blob/main/wordforms_added_manually.json): missing word forms for some contentious labels were added manually
-	[getting_query_terms.ipynb](https://github.com/cultural-ai/wordsmatter/blob/main/getting_query_terms.ipynb): generating a list of query terms for every contentious label; [query_terms_cont_en.json](https://github.com/cultural-ai/wordsmatter/blob/main/query_terms_cont_en.json): English query terms, [query_terms_cont_nl.json](https://github.com/cultural-ai/wordsmatter/blob/main/query_terms_cont_nl.json): Dutch query terms; 

2. Querying LOD-resources:
–	Wikidata, Getty AAT, Princeton WordNet were queried using their web-interface
–	Querying NMVW: see the directory [NMVW](https://github.com/cultural-ai/wordsmatter/tree/main/NMVW) 

3. Selecting related matched in every resource based on guidelines:
–	all related matches rep resource per contentious label: [rm.csv](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/rm.csv), [rm.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/rm.json)
–	synsets from Princeton WordNet 3.1 are mapped to PWNIDs: [synset2pwnid_mappings.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/synset2pwnid_mappings.json) 

4. Getting literal values of related matches in every resource
–	see the module [LODlitParser](https://github.com/cultural-ai/wordsmatter/tree/main/LODlitParser)
–	the resulting files: [aat_rm_en.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/aat_rm_en.json), [aat_rm_nl.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/aat_rm_nl.json), [wikidata_rm_en.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/wikidata_rm_en.json), [wikidata_rm_nl.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/wikidata_rm_nl.json), [pwn_rm.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/pwn_rm.json), [nmvw_rm.json](https://github.com/cultural-ai/wordsmatter/blob/main/related_matches/nmvw_rm.json).

Contentious labels are linked to the URIs of their related matches with the property skos:relatedMatch.
