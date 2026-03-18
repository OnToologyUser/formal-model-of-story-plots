# Story Plot Ontology

A modular OWL ontology for representing story plots. The ontology models characters, places, temporal relations, events, social relations, narrative structure, and actions. Ontology is used in instances from the [Narn i Chîn Húrin](https://en.wikipedia.org/wiki/The_Children_of_H%C3%BArin).

## Structure

The ontology consists of seven modules (`place.ttl`, `rcc.ttl`, `time.ttl`, `social.ttl`, `event.ttl`, `plot.ttl`, `actions.ttl`) and one instance file `narn-instances.ttl` that extends the `narn.ttl`. The modules `meo.ttl` and `fo.ttl` are external dependencies.

## Tools

[Claude Opus 4.6](https://www.anthropic.com/claude/opus) was used as the AI tool in the project. It was used for ontology design discussions, and logical consistency.

[Protégé](https://protege.stanford.edu/) with the [HermiT reasoner](http://www.hermit-reasoner.com/) was used to verify consistency of all modules.

[RDFox](https://www.oxfordsemantic.tech/rdfox) was used as a triple store to load all modules together and run SPARQL queries against the knowledge base, for validating that competency questions are answerable.

[WIDOCO](https://github.com/dgarijo/Widoco) was used to generate HTML documentation from the ontology annotations.

[OnToology](http://ontoology.linkeddata.es/) was used to automate the documentation and manage persistent identifiers.

## Design Choices

Narrative structure is modelled through [Freytag’s Pyramid](https://en.wikipedia.org/wiki/Plot_(narrative)#Gustav_Freytag). A story is organised into five stages including Exposition, Rising Action, Climax, Falling Action, and Resolution (Denouement). These stages are subclasses of NarrativeElement, and each Story includes at least one Climax and one Resolution.

The ontology also includes narrative concepts introduced by [Aristotle in Poetics](https://en.wikipedia.org/wiki/Poetics_(Aristotle)). Anagnorisis is represented as a PlotDevice corresponding to a discovery event, whereas Peripeteia denotes a reversal of fortune. A TragicHero is defined as a Protagonist who undergoes Peripeteia in accordance with Aristotelian tragedy.

 Temporal relations follow the system of interval relations from [Allen’s temporal algebra](https://www.emse.fr/~zimmermann/Teaching/KRR/allen.html) and are defined with logical characteristics including transitivity, symmetry, asymmetry, and irreflexivity. 
 
 Spatial relations are structured according to the [Region Connection Calculus](https://www.emse.fr/~zimmermann/Teaching/KRR/rcc.html) and include the spatial relations DC, EC, PO, EQ, TPP, TPPi, NTPP, and NTPPi. 
 
 Actions are treated separately from events following [Davidson’s Actions, Reasons, and Causes](https://academicweb.nd.edu/~jspeaks/courses/2008-9/43503/_LECTURES/davidson-causal-theory.pdf). Actions are considered intentional events and are characterised by an agent, a target, an instrument, an intention, and a result.