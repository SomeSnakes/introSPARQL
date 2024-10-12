|Annexe 1|Réponses DBpedia|
|:--:|:--:|
## Exercice 1
### a)
SELECT DISTINCT ?livre ?auteur

WHERE
{
?livre rdf:type dbo:Book ;
dbo:author ?auteur
}

### b)
SELECT DISTINCT ?livre ?auteur

WHERE
{
?livre rdf:type dbo:Book ;
dbo:author ?auteur
}
ORDER BY ?auteur

## Exercice 2
SELECT DISTINCT ?auteur

WHERE
{
?auteur rdfs:label "Agatha Christie"@en
}

## Exercice 3
SELECT DISTINCT ?livre ?year

WHERE
{
?livre rdf:type dbo:Book ;
dbp:years ?year
FILTER (?year > 1900)
}

## Exercice 4
SELECT DISTINCT ?livre ?year

WHERE
{
?livre rdf:type dbo:Book ;
dbp:years ?year
FILTER (?year > 1900)
FILTER (?year < 1910)
}

## Exercice 5
### a)
SELECT DISTINCT ?livre ?auteur

WHERE
{
?livre rdf:type dbo:Book ;
dbo:author ?auteur
FILTER REGEX(?auteur, "agatha_christie", "i")
}

### b)
SELECT DISTINCT ?livre ?year ?auteur

WHERE
{
?livre rdf:type dbo:Book ;
dbo:author ?auteur ;
dbo:releaseDate ?year
FILTER REGEX(?auteur, "agatha_christie", "i")
}