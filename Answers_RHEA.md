## Exercice 6
### a)
SELECT DISTINCT ?reaction ?equation

WHERE

{
  ?reaction rdfs:subClassOf rh:Reaction
}

  ORDER BY ?reaction

### b)
SELECT DISTINCT ?reaction ?equation

WHERE

{
  ?reaction rdfs:subClassOf rh:Reaction .
  ?reaction rh:status rh:Approved .
  ?reaction rh:equation ?equation
}

  ORDER BY ?reaction

  ## Exercice 7

PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX rh:<http://rdf.rhea-db.org/>
PREFIX ch:<http://purl.obolibrary.org/obo/>

SELECT ?reaction ?equation
WHERE 
{
  ?reaction rdfs:subClassOf rh:Reaction .
  ?reaction rh:status rh:Approved .
  
  ?reaction rh:side ?reaction1 .
  ?reaction1 rh:contains ?participant1 .
  ?participant1 rh:compound ?compound1 .
  ?compound1 rh:chebi ch:CHEBI_30616 .

}

## Exercice 8


SELECT ?reaction ?equation
WHERE 
{
  ?reaction rdfs:subClassOf rh:Reaction .
  ?reaction rh:status rh:Approved .
  ?reaction rh:equation ?equation .
  
  ?reaction rh:side ?reaction1 .
  ?reaction1 rh:contains ?participant1 .
  ?participant1 rh:compound ?compound1 .
  ?compound1 rh:chebi ch:CHEBI_30616 .
  
    ?reaction rh:side ?reaction2 .
  ?reaction2 rh:contains ?participant2 .
  ?participant2 rh:compound ?compound2 .
  ?compound2 rh:chebi ch:CHEBI_456216 .
  
  ?reaction1 rh:transformableTo ?reaction2 .
  
  }

  ## Exercice 9
  SELECT DISTINCT ?species

WHERE

{
SERVICE <http://sparql.uniprot.org/sparql>
	{
    ?species a up:Taxon .
	}
}

  ORDER BY ?species