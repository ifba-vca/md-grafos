# md-grafos

> Baseado no artigo [Graph and its representations](https://www.geeksforgeeks.org/graph-and-its-representations/) esse repositório possui um compilado de projetos em estrutura de dados para o estudo dos grafos.

Podemos algoritmos de grafos de duas formas: por uma lista de ajacência ou por uma matrix de ajacência.

# Matriz de adjacência

A matriz de adjacência é uma tabela 2D de tramanho VxV, onde V é o númro de vértices em um grafo. Podemos representar 0 como não adjacente e 1 como adjacente. Observe o grafo abaixo:

![001](https://user-images.githubusercontent.com/13178261/158931245-7f357fa4-1c41-4e54-ae34-7ca02b9b539b.png)

Montando uma matriz VxV de adjecência, podemos monta-la da seguinte forma:

![002](https://user-images.githubusercontent.com/13178261/158931256-0359a084-5189-4948-885f-c130639aff8b.png)

Pensendo nessa perspectiva, podemos imaginar um objeto `Graph` (grafo em inglês, que possui as seguintes informações: total de vertices `vertex`, total de arestas `edges` e vetor de nós `nodes`.

> ⚠️ Vale lembrar que vetor é um brupo de valores que pode ser unidimensional: `[1,2,3,4]`, bidimensional: `[[1,2],[2,4]]`, até a n dimensões.

Podemos definir esse objeto com a seguinte classe

```python
class Graph:
  vertex = None
  edge = None
  nodes = []
  
  def __init__(self, vertex, edge):
    self.vertex = vertex
    self.edge = edge
    self.nodes = [[0 for i in range(vertex)] for j in range(vertex)]

```

Perceba que a classe quando inciada, começa setando todas as variáveis com o valor 0. Dado um grafo `G1` cujo o número de arestas é 4 e de vertices 5, ao criar o grafo, ele criará o seguinte array:

```
[ [0,0,0,0,0],
  [0,0,0,0,0],
  [0,0,0,0,0],
  [0,0,0,0,0],
  [0,0,0,0,0],
]
```

# Lista de adjacência

