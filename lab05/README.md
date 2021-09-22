# Aluno
* 240013: Lucas Jacinto Gonçalves

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução
~~~cypher
MATCH (n:Marcador) -[:Pertence]->(m:Categoria {id: "Serviços"})
RETURN n
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução
~~~cypher
MATCH (p:Marcador)-[:Pertence]->()-[:Superior*0..]->(k:Categoria {id:"Serviços"})
RETURN p
~~~
