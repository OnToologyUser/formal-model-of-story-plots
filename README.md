# Story Plot Ontology

A modular OWL ontology for representing story plots. The ontology models characters, places, temporal relations, events, social relations, narrative structure, and actions. Ontology is used in instances from the [Narn i Chîn Húrin](https://en.wikipedia.org/wiki/The_Children_of_H%C3%BArin).

## Structure

The ontology consists of seven modules (`place.ttl`, `rcc.ttl`, `time.ttl`, `social.ttl`, `event.ttl`, `plot.ttl`, `actions.ttl`) and one instance file (`narn-instances.ttl`) that extends the `narn.ttl`. The modules `meo.ttl` and `fo.ttl` are external dependencies.

## Tools

[Claude Opus 4.6](https://www.anthropic.com/claude/opus) was used as the AI tool in the project. It was used for ontology design discussions, and logical consistency.
[Protégé](https://protege.stanford.edu/) with the [HermiT reasoner](http://www.hermit-reasoner.com/) was used to verify [OWL 2 DL](https://www.w3.org/TR/owl2-overview/) consistency of all modules.
[RDFox](https://www.oxfordsemantic.tech/rdfox) was used as a triple store to load all modules together and run SPARQL queries against the combined knowledge base, for validating that competency questions are answerable.
[WIDOCO](https://github.com/dgarijo/Widoco) was used to generate HTML documentation from the ontology annotations.