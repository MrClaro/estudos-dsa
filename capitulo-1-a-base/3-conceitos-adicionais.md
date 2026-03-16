# Conceitos Adicionais

<!--toc:start-->

- [Conceitos Adicionais](#conceitos-adicionais)
  - [Ponteiros e Referências](#ponteiros-e-referências)
  - [Recursão](#recursão)
  - [Iteração](#iteração)
  - [Tipos de Dados e Tamanho em Bytes](#tipos-de-dados-e-tamanho-em-bytes)
    <!--toc:end-->

## Ponteiros e Referências

Em linguagens atuais como TypeScript e Java, não lidamos diretamente com ponteiros (endereços de memória editáveis) como em C ou C++. No entanto, o conceito de **referências** é fundamental.

Quando você atribui um objeto a uma variável, na verdade está criando uma referência a esse objeto no **Heap**. Isso significa que a variável não contém o "valor" em si, mas sim o **endereço** de onde o valor está armazenado.

- **Impacto prático:** Se você modificar o objeto através de uma variável, todas as outras variáveis que referenciam o mesmo endereço também verão essa modificação, pois todas apontam para o mesmo lugar na RAM.

## Recursão

A recursão é uma técnica onde uma função chama a si mesma para resolver um problema. Ela é composta por dois elementos principais:

1. **Condição de parada (Caso Base):** É o cenário que interrompe as chamadas, evitando que a função rode infinitamente.
2. **Chamada recursiva:** Onde a função invoca a si mesma com um subconjunto menor do problema original.

Toda vez que uma função chama a si mesma, ela empilha um novo _frame_ na **Pilha de Chamadas (Call Stack)**. Se a recursão for muito profunda e não atingir a condição de parada, a pilha esgota seu espaço, gerando o erro de **Stack Overflow**.

## Iteração

A iteração é a repetição de um bloco de código usando estruturas de controle como loops (`for`, `while`).

- **Diferença da Recursão:** Ao contrário da recursão, a iteração geralmente ocorre dentro de um único frame da Stack (ou reaproveita o mesmo espaço), não criando novas chamadas de função. Por isso, é mais eficiente em termos de memória e não corre o risco de estourar a pilha, sendo preferível para processamentos muito longos.

## Tipos de Dados e Tamanho em Bytes

Cada tipo de dado ocupa um espaço específico na RAM. Entender isso é o que nos permite entender por que o acesso a um Array é **$O(1)$**. O computador usa uma fórmula matemática simples para encontrar qualquer elemento instantaneamente:

$$\text{Endereço} = \text{Início do Array} + (\text{Índice} \times \text{Tamanho do Tipo})$$

**Exemplo Prático:**
Em Java, um `int` ocupa 4 bytes. Se um array começa no endereço `1000` e você quer o índice `5`, o computador faz: $1000 + (5 \times 4) = 1020$.

Vale ressaltar que esse "Início do Array" é algo que não controlamos diretamente, ou seja, não temos acesso a esse valor em sua forma pura, mas o sistema operacional e a JVM cuidam disso para nós, abstraindo esses valores e fazendo as contas. O importante é entender que o acesso é direto e constante, independentemente do tamanho do array.

### Tamanhos em JavaScript / TypeScript (Aproximados)

- **Number**: 8 bytes (64 bits - padrão IEEE 754).
- **String**: 2 bytes por caractere (UTF-16).
- **Boolean**: Geralmente 4 bytes (para alinhamento de memória).
- **Null / Undefined**: 0 bytes (representam ausência de valor, onde null é um valor atribuido e undefined é um valor que não foi atribuido ainda).
- **Object / Array**: Variam conforme o conteúdo, armazenando referências no Heap.

### Tamanhos em Java (Tipos Primitivos Fixos)

| Tipo        | Tamanho | Descrição                               |
| ----------- | ------- | --------------------------------------- |
| **byte**    | 1 byte  | 8 bits                                  |
| **short**   | 2 bytes | 16 bits                                 |
| **int**     | 4 bytes | 32 bits                                 |
| **long**    | 8 bytes | 64 bits                                 |
| **float**   | 4 bytes | Precisão simples                        |
| **double**  | 8 bytes | Precisão dupla                          |
| **char**    | 2 bytes | Caractere Unicode                       |
| **boolean** | 1 byte  | (Depende da JVM, mas 1 byte é o padrão) |

---

> [!TIP]
> Ao passar um **primitivo** (como um `int`) para uma função, você passa uma **cópia** (valor). Ao passar um **objeto** ou **array**, você passa a **referência**. Se você alterar o array dentro da função, ele mudará fora dela também!
