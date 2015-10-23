# RDF for Object-oriented heads
RDF for people used to Object-oriented programming (OOP)

## status

**For now just a skrach book to collect notes**

## recommended reading

* http://www.w3.org/TR/rdf11-primer/
* http://patterns.dataincubator.org/book/

## topics

### open world assumption

https://en.wikipedia.org/wiki/Open-world_assumption

### anyone can say anything about anything

http://www.w3.org/TR/2002/WD-rdf-concepts-20020829/#xtocid48014

### follow your nose

http://patterns.dataincubator.org/book/follow-your-nose.html

### classes and properties

from https://github.com/valueflows/agent/issues/15#issuecomment-148893163

> "we can define new properties ourself, and recommend using them on various existing classes"

> Since rdf:Property doesn't stay 'inside' owl:Class and has its full autonomy! Actually properties define their relationships to classes (eg. rdfs:domain and rdfs:range) and I can't really think of example where class would define relationship to some properties.


### types or classes 

from https://github.com/valueflows/agent/pull/49#issuecomment-150507316

> Something to always keep in mind, each instance can have assertions of belonging to any number of sets `"@type": [ "vf:Resource", "schema:Book", "foo:Novel", "gr:Product" ]` etc.
So one would never in code check `thing["@type"] === helper.expand("schema:Book")` but always assume that it can have any number of types (even 50 or 100, especially if it has [materialized inferences](http://patterns.dataincubator.org/book/materialize-inferences.html)) and instead always check `thing["@type"].includes(helper.expand("schema:Book"))`. Most likely libraries specific to different programming languages, define nicer idiomatic interfaces and don't hack directly around how they represent raw JSON structures in their runtime.
