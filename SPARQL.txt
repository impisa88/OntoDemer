##  query 1 - Dado um comportamento, quais riscos a saúde são suscetíveis?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?behavior ?illness WHERE {
	?behavior my:Results ?illness.
}

##  query 2 - Dado um cadeirante, a que riscos a saúde ele é suscetível?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?person ?behavior ?illness ?susceptibility WHERE {
	?person owl:sameAs my:PWD_1.
	?person my:behaviors ?behavior.
	?behavior rdf:type my:Harmful_Behavior.
	?behavior my:Results ?illness.
	?behavior my:susceptibilities ?susceptibility	
}

## query 3 - Dado um cadeirante, quais comportamentos aumentam a probabilidade de desenvolver um risco a saúde?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?person ?behavior ?illness ?susceptibility WHERE {
	?person owl:sameAs my:PWD_1.
	?person my:behaviors ?behavior.
	?behavior rdf:type my:Harmful_Behavior.
	?behavior my:Results ?illness.
	?behavior my:susceptibilities ?susceptibility.
	?susceptibility rdf:type my:High_Susceptibility 
}

## query 4 - Dado um cadeirante, que comportamento preventivo ele precisa fazer?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
prefix my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?person ?illness ?recommendation WHERE { 
	?person owl:sameAs my:PWD_3.
	?person my:illness ?illness.
	?person my:do ?recommendation
}


## query 5 - reavaliar



## query 6 - Dada uma deficiência quais outros riscos a saúde são consequentes?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?disorder ?illness WHERE {
	?disorder owl:sameAs my:Paraplegia.
	?illness my:relatedIllness ?disorder	
}

## query 7 - Dado uma patologia, quais atividades diminuem a probabilidade de maiores riscos a saúde?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?behavior ?recommendation WHERE {
	?behavior my:recommendations ?recommendation.
}



