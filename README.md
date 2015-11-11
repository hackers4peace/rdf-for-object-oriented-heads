# RDF for Object-oriented heads
RDF for people used to Object-oriented programming (OOP)

## status

**For now just a skrach book to collect notes**

## recommended reading

* http://www.w3.org/TR/rdf11-primer/
* http://linkeddatabook.com/book
* http://patterns.dataincubator.org/book/

## topics

### open world assumption

https://en.wikipedia.org/wiki/Open-world_assumption

### anyone can say anything about anything

http://www.w3.org/TR/2002/WD-rdf-concepts-20020829/#xtocid48014

### follow your nose

http://patterns.dataincubator.org/book/follow-your-nose.html

### opaque URIs

http://www.w3.org/DesignIssues/Axioms.html#opaque

### Cool URIs don't change

http://www.w3.org/Provider/Style/URI.html

### classes and properties

from https://github.com/valueflows/agent/issues/15#issuecomment-148893163

> "we can define new properties ourself, and recommend using them on various existing classes"

> Since rdf:Property doesn't stay 'inside' owl:Class and has its full autonomy! Actually properties define their relationships to classes (eg. rdfs:domain and rdfs:range) and I can't really think of example where class would define relationship to some properties.

while it seams that definition of clases can have their semantics dependent on existance of some properties 

eg. https://github.com/valueflows/agent/issues/38#issuecomment-150543678

> If we define vf:Transfer (not the physical one - sth:Transport) as "An vf:Agent (individual or group), who have ownership over a resource, passes this ownership onto another agent". I don't see a way to define shared concept of Transfer without first defining shared concept of ownership. In other worlds, unless we agree on shared generic owns/owner relation between agent and resource, it seems to me that we can forget about defining shared generic concept of Transfer ( and later Exchange dependent on definition of Transfer )


### types or classes 

from https://github.com/valueflows/agent/pull/49#issuecomment-150507316

> Something to always keep in mind, each instance can have assertions of belonging to any number of sets `"@type": [ "vf:Resource", "schema:Book", "foo:Novel", "gr:Product" ]` etc.
So one would never in code check `thing["@type"] === helper.expand("schema:Book")` but always assume that it can have any number of types (even 50 or 100, especially if it has [materialized inferences](http://patterns.dataincubator.org/book/materialize-inferences.html)) and instead always check `thing["@type"].includes(helper.expand("schema:Book"))`. Most likely libraries specific to different programming languages, define nicer idiomatic interfaces and don't hack directly around how they represent raw JSON structures in their runtime.
