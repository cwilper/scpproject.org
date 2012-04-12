# Namespaces
@prefix owl:  <http://www.w3.org/2002/07/owl#> .
@prefix rdf:  <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix scp:  <http://scpproject.org/terms/#> .

# Classes
scp:Bytestream      rdf:type        owl:Class .
scp:ContentLocation rdf:type        owl:Class .
scp:ResolvableURI   rdfs:subClassOf scp:ContentLocation .
scp:PackagePath     rdfs:subClassOf scp:ContentLocation .
scp:Package         rdf:type        owl:Class .
scp:PackageType     rdf:type        owl:Class .

# Properties
scp:location  rdf:type    owl:ObjectProperty ;
              rdfs:domain scp:Bytestream ;
              rdfs:range  scp:ContentLocation .
scp:path      rdf:type    owl:DatatypeProperty ,
                          owl:FunctionalProperty ;
              rdfs:domain scp:PackagePath ;
              rdfs:range  rdf:PlainLiteral .
scp:inPackage rdf:type    owl:ObjectProperty ,
                          owl:FunctionalProperty ;
              rdfs:domain scp:PackagePath ;
              rdfs:range  scp:Package .
scp:type      rdf:type    owl:ObjectProperty ;
              rdfs:domain scp:Package ;
              rdfs:range  scp:PackageType .
