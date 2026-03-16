# Estruturas de Dados

<!--toc:start-->

- [Estruturas de Dados](#estruturas-de-dados)
  - [Introdução](#introdução)
  - [Estruturas de Dados Lineares mais comuns](#estruturas-de-dados-lineares-mais-comuns)
  - [Estruturas de Dados Não Lineares mais comuns](#estruturas-de-dados-não-lineares-mais-comuns)
  - [Resumo de Complexidade (Time Complexity)](<#resumo-de-complexidade-(time-complexity)>)
  <!--toc:end-->

## Introdução

O primeiro ponto para estudar DSA é entender que as estruturas se dividem em **lineares** e **não lineares**.

- **Lineares:** Os elementos estão organizados em uma sequência lógica, onde cada item tem um predecessor e um sucessor (exceto o primeiro e o último). A travessia dos dados ocorre de forma sequencial.
- **Não Lineares:** Os elementos estão organizados de forma hierárquica ou interconectada (como Árvores e Grafos). Um elemento pode se conectar a múltiplos outros, não seguindo uma linha única.

## Estruturas de Dados Lineares mais comuns

- **Array**: Uma coleção de elementos do mesmo tipo(caso homogênea), armazenados em posições contíguas na memória. O acesso a qualquer elemento é feito em tempo constante $O(1)$, pois o endereço pode ser calculado diretamente via índice.
- **Linked List (Lista Encadeada)**: Uma coleção de nós onde cada um contém o dado e uma referência (ponteiro) para o próximo. O acesso é $O(n)$, mas a inserção e remoção podem ser mais eficientes que no Array em certos cenários, pois não exigem o deslocamento de todos os elementos.
- **Stack (Pilha)**: Segue o princípio **LIFO** (_Last In, First Out_). Operações principais como `push` e `pop` são $O(1)$.
- **Queue (Fila)**: Segue o princípio **FIFO** (_First In, First Out_). Operações como `enqueue` e `dequeue` são $O(1)$.
- **Deque (Double-Ended Queue)**: Uma fila de "duas pontas" onde você pode inserir ou remover tanto do início quanto do fim em tempo constante $O(1)$.

## Estruturas de Dados Não Lineares mais comuns

- **Tree (Árvore)**: Uma estrutura hierárquica onde cada nó tem um valor e referências para seus filhos. É fundamental para representar hierarquias e otimizar buscas (como a _Binary Search Tree_).
- **Graph (Grafo)**: Uma coleção de nós (vértices) e conexões (arestas) entre eles. Essencial para representar redes sociais, mapas e caminhos. As travessias principais são **DFS** (Busca em Profundidade) e **BFS** (Busca em Largura).
- **Hash Table (Tabela Hash)**: Estrutura que mapeia chaves a valores através de uma função de hash. É a base dos `Objects` em JS e `HashMap` em Java. Oferece, em média, performance $O(1)$ para quase tudo.

## Resumo de Complexidade (Time Complexity)

| Estrutura       | Acesso      | Busca       | Inserção    | Remoção     |
| --------------- | ----------- | ----------- | ----------- | ----------- |
| **Array**       | $O(1)$      | $O(n)$      | $O(n)$      | $O(n)$      |
| **Linked List** | $O(n)$      | $O(n)$      | $O(1)$      | $O(1)$      |
| **Stack/Queue** | $O(n)$      | $O(n)$      | $O(1)$      | $O(1)$      |
| **Hash Table**  | $N/A$       | $O(1)$      | $O(1)$      | $O(1)$      |
| **BST (Média)** | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ |
