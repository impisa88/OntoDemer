##  CQ1 - What are the health risks associated with a given behavior?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?behavior ?illness WHERE {
	?behavior my:Results ?illness.
}



## CQ2 - What health risks is a wheelchair user susceptible to?

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



## CQ3 - Which behaviors increase the likelihood of developing a health risk for a wheelchair user?

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



## CQ4 - What preventive behaviors should a wheelchair user engage in?

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


## CQ5 - What additional health risks may arise as a consequence of a disability?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?disorder ?illness WHERE {
	?disorder owl:sameAs my:Paraplegia.
	?illness my:relatedIllness ?disorder	
}



## CQ6 - Which activities reduce the likelihood of major health risks given a disability?

PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX my: <http://www.semanticweb.org/jgh88/ontologies/2023/8/untitled-ontology-3#>

SELECT distinct ?behavior ?recommendation WHERE {
	?behavior my:recommendations ?recommendation.
}



