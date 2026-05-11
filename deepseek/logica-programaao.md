```markdown

\# Lógica de Programação: Do zero às estruturas essenciais



Bem-vindo(a) a este guia de lógica de programação. Aqui você vai percorrer os conceitos fundamentais que formam a base de qualquer linguagem e de qualquer programa. O objetivo é construir um raciocínio sólido, com muitos exemplos práticos, independentemente da linguagem que você usará no futuro.



\*\*Como ler este material\*\*  

Os exemplos são escritos em uma sintaxe próxima à de Python, por ser clara e direta. Mas os conceitos são universais. A cada tópico, há pequenos desafios para você testar o seu entendimento.



\---



\## 1. O que é um programa?



Um programa é uma sequência de instruções que o computador executa para resolver um problema. Essas instruções manipulam \*\*dados\*\* (números, textos, listas) e tomam \*\*decisões\*\* baseadas em condições. A lógica de programação é a arte de organizar essas instruções de forma correta, eficiente e compreensível.



\---



\## 2. Variáveis e tipos de dados



\### 2.1 Variáveis: como guardar informação



Uma variável é um espaço na memória que guarda um valor. Você escolhe um nome (identificador) e atribui um valor a ele. O nome deve ser significativo.



```python

idade = 25

nome = "Maria"

altura = 1.68

```



Aqui, `idade`, `nome` e `altura` são variáveis. O sinal `=` é o operador de atribuição: ele coloca o valor da direita dentro da variável da esquerda.



\### 2.2 Tipos primitivos



Os dados que uma variável pode guardar possuem tipos diferentes. Os mais comuns são:



| Tipo | Exemplo | Descrição |

|------|---------|-----------|

| Inteiro (`int`) | `42`, `-7` | Números sem parte decimal |

| Ponto flutuante (`float`) | `3.14`, `-0.5` | Números com casas decimais |

| Texto (`string`) | `"Olá"`, `'mundo'` | Sequência de caracteres |

| Booleano (`bool`) | `True`, `False` | Verdadeiro ou falso |



Exemplo:

```python

quantidade = 10          # int

preco = 29.90            # float

mensagem = "Bom dia"     # string

ativo = True             # bool

```



\*\*Por que os tipos importam?\*\*  

Cada operação espera determinados tipos. Somar um número com um texto, por exemplo, não faz sentido sem uma conversão explícita.



```python

\# conversão de tipos

ano = 2025

texto\_ano = str(ano)            # "2025"

proximo = int("2026")           # 2026

altura = float("1.75")          # 1.75

```



> \*\*Desafio rápido:\*\* Crie variáveis para armazenar o nome de um produto, sua quantidade em estoque, seu preço unitário e se ele está disponível para venda.



\### 2.3 Nomes de variáveis e boas práticas



\- Use letras, números e sublinhado (`\_`). Não use espaços ou caracteres especiais.

\- Comece com letra minúscula e separe palavras com `\_` (snake\_case): `valor\_total`, `data\_nascimento`.

\- Escolha nomes que revelem o propósito da variável.



\---



\## 3. Operadores e expressões



\### 3.1 Operadores aritméticos



| Operador | Significado | Exemplo (`a = 10`, `b = 3`) |

|----------|-------------|-----------------------------|

| `+` | Adição | `a + b` → `13` |

| `-` | Subtração | `a - b` → `7` |

| `\*` | Multiplicação | `a \* b` → `30` |

| `/` | Divisão (real) | `a / b` → `3.333...` |

| `//` | Divisão inteira | `a // b` → `3` |

| `%` | Módulo (resto) | `a % b` → `1` |

| `\*\*` | Exponenciação | `a \*\* b` → `1000` |



```python

nota1 = 8.5

nota2 = 7.0

media = (nota1 + nota2) / 2

```



\### 3.2 Operadores relacionais e lógicos



Servem para comparar valores e combinar condições. O resultado é sempre um booleano (`True` ou `False`).



\*\*Relacionais:\*\* `==` (igual), `!=` (diferente), `>`, `<`, `>=`, `<=`.



\*\*Lógicos:\*\* `and` (e), `or` (ou), `not` (não).



Exemplo:

```python

idade = 20

tem\_carteira = True



pode\_dirigir = idade >= 18 and tem\_carteira  # True

```



\*\*Tabela verdade rápida:\*\*



| `A` | `B` | `A and B` | `A or B` | `not A` |

|-----|-----|-----------|----------|---------|

| True | True | True | True | False |

| True | False | False | True | False |

| False | True | False | True | True |

| False | False | False | False | True |



> \*\*Desafio:\*\* Escreva uma expressão que seja verdadeira se um número estiver entre 10 e 20 (inclusive).



\---



\## 4. Estruturas de controle



As estruturas de controle ditam o fluxo de execução do programa. Elas permitem tomar decisões e repetir blocos de código.



\### 4.1 Condicionais: `if`, `else if` (`elif`), `else`



```python

nota = 8.0



if nota >= 9.0:

&#x20;   print("Excelente")

elif nota >= 7.0:

&#x20;   print("Bom")

elif nota >= 5.0:

&#x20;   print("Regular")

else:

&#x20;   print("Insuficiente")

```



O computador avalia cada condição na ordem. Quando uma é verdadeira, executa o bloco correspondente e ignora o restante. O `else` captura qualquer caso não tratado.



\*\*Blocos e indentação:\*\* Em Python, os blocos são definidos por indentação (espaços no início da linha). Em outras linguagens usa-se chaves `{}`, mas a ideia é a mesma.



\### 4.2 Laços de repetição



\#### 4.2.1 `while` (enquanto)



Repete um bloco enquanto uma condição for verdadeira.



```python

contador = 0

while contador < 5:

&#x20;   print(contador)

&#x20;   contador = contador + 1

\# Imprime 0, 1, 2, 3, 4

```



\*\*Cuidado com loops infinitos!\*\* Sempre garanta que a condição se tornará falsa em algum momento.



\#### 4.2.2 `for` (para cada)



Usado para percorrer uma sequência (como uma lista ou um intervalo numérico).



```python

\# intervalo de 0 a 4

for i in range(5):

&#x20;   print(i)



\# percorrendo uma lista de nomes

nomes = \["Ana", "Bruno", "Carla"]

for nome in nomes:

&#x20;   print("Olá, " + nome)

```



A função `range(início, fim, passo)` gera números inteiros. Exemplo: `range(2, 10, 2)` → 2, 4, 6, 8.



\#### 4.2.3 Controle de fluxo nos laços: `break` e `continue`



\- `break`: interrompe o laço imediatamente.

\- `continue`: pula para a próxima iteração.



```python

for i in range(10):

&#x20;   if i == 3:

&#x20;       continue   # pula o 3

&#x20;   if i == 7:

&#x20;       break      # para no 7

&#x20;   print(i)

\# Saída: 0, 1, 2, 4, 5, 6

```



> \*\*Desafio:\*\* Escreva um programa que calcule a soma de todos os números pares de 1 a 100 usando um laço `for` e uma condicional.



\---



\## 5. Funções



Funções são blocos de código reutilizáveis que realizam uma tarefa específica. Recebem parâmetros (entrada), processam e podem devolver um resultado (saída). Tornam o código mais organizado, legível e modular.



\### 5.1 Definindo e chamando funções



```python

def saudacao(nome):

&#x20;   return "Olá, " + nome + "!"



mensagem = saudacao("João")

print(mensagem)   # Olá, João!

```



\- `def`: palavra-chave para definir.

\- `nome`: parâmetro da função.

\- `return`: valor devolvido (se omitido, a função retorna `None`).



\### 5.2 Parâmetros e argumentos



```python

def soma(a, b):

&#x20;   return a + b



resultado = soma(3, 4)   # 7

```



Você pode ter parâmetros com valores padrão:

```python

def aumentar\_preco(valor, percentual=10):

&#x20;   return valor \* (1 + percentual/100)



preco1 = aumentar\_preco(100)        # 110.0 (usa 10%)

preco2 = aumentar\_preco(100, 20)    # 120.0 (sobrescreve 20%)

```



\### 5.3 Escopo de variáveis



Variáveis criadas dentro de uma função têm \*\*escopo local\*\*: só existem ali. Variáveis fora da função estão no escopo global, mas alterá-las dentro da função requer cuidado (use `global` apenas quando necessário).



```python

x = 5   # global



def exemplo():

&#x20;   y = 10  # local

&#x20;   print(x)  # acessa a global, 5

&#x20;   # x = 20  # isso criaria uma nova variável local, a menos que declarado global



exemplo()

```



> \*\*Desafio:\*\* Crie uma função `e\_par(numero)` que retorne `True` se o número for par e `False` caso contrário.



\---



\## 6. Recursão



Recursão é a técnica onde uma função chama a si mesma para resolver versões menores do mesmo problema. Toda função recursiva precisa de:



1\. \*\*Caso base:\*\* condição que interrompe a recursão (evita loop infinito).

2\. \*\*Caso recursivo:\*\* chama a si mesma com uma entrada reduzida.



\### 6.1 Exemplo clássico: fatorial



Fatorial de `n` (n!) é o produto de todos os inteiros positivos de 1 a `n`.  

`0! = 1` (caso base). Para `n > 0`: `n! = n \* (n-1)!`.



```python

def fatorial(n):

&#x20;   if n == 0:

&#x20;       return 1                 # caso base

&#x20;   else:

&#x20;       return n \* fatorial(n - 1)  # caso recursivo



print(fatorial(5))  # 120

```



\*\*Rastreamento:\*\*

```

fatorial(5)

→ 5 \* fatorial(4)

→ 5 \* (4 \* fatorial(3))

→ 5 \* (4 \* (3 \* fatorial(2)))

→ 5 \* (4 \* (3 \* (2 \* fatorial(1))))

→ 5 \* (4 \* (3 \* (2 \* (1 \* fatorial(0)))))

→ 5 \* (4 \* (3 \* (2 \* (1 \* 1)))) = 120

```



\### 6.2 Outro exemplo: sequência de Fibonacci



`fib(0) = 0`, `fib(1) = 1`, e para `n >= 2`: `fib(n) = fib(n-1) + fib(n-2)`.



```python

def fibonacci(n):

&#x20;   if n == 0:

&#x20;       return 0

&#x20;   elif n == 1:

&#x20;       return 1

&#x20;   else:

&#x20;       return fibonacci(n-1) + fibonacci(n-2)



for i in range(10):

&#x20;   print(fibonacci(i), end=" ")  # 0 1 1 2 3 5 8 13 21 34

```



\*\*Atenção:\*\* A versão recursiva simples de Fibonacci é ineficiente para valores grandes (muitas chamadas repetidas). Depois veremos como a análise de complexidade ajuda a perceber isso.



> \*\*Desafio:\*\* Implemente uma função recursiva que calcule a soma dos números de 1 a `n`. Exemplo: soma(5) → 15.



\---



\## 7. Estruturas de dados básicas



Estruturas de dados organizam e armazenam dados de maneiras diferentes, adequadas a cada tipo de problema. As três estruturas fundamentais são listas, filas e pilhas. Vamos abordá-las de forma simples.



\### 7.1 Listas (arrays sequenciais)



Uma lista é uma coleção ordenada e mutável de itens. Em Python, chamamos de `list`.



```python

frutas = \["maçã", "banana", "laranja"]

frutas.append("uva")           # adiciona no final

frutas.insert(1, "abacaxi")    # insere na posição 1

frutas.remove("banana")        # remove pelo valor

print(frutas\[0])               # "maçã"

print(len(frutas))             # tamanho: 3

```



Percorrer uma lista com `for` é muito comum. Posso acessar qualquer elemento diretamente pelo índice (ex: `frutas\[2]`). Listas são a base para muitas outras estruturas.



\### 7.2 Pilha (Stack)



Uma pilha segue o princípio \*\*LIFO\*\* (\*Last In, First Out\* – o último a entrar é o primeiro a sair). Pense em uma pilha de pratos: você coloca no topo e retira do topo.



Operações principais:

\- `push`: adicionar ao topo.

\- `pop`: remover do topo.

\- `peek` (ou top): consultar o topo sem remover.



```python

pilha = \[]

pilha.append("A")      # push A

pilha.append("B")      # push B

pilha.append("C")      # push C

print(pilha.pop())     # C (último a entrar)

print(pilha\[-1])       # peek: "B"

```



Aplicações: controle de desfazer/refazer, navegação entre páginas, verificação de parênteses.



\### 7.3 Fila (Queue)



Uma fila segue o princípio \*\*FIFO\*\* (\*First In, First Out\* – o primeiro a entrar é o primeiro a sair), como uma fila de banco.



Operações:

\- `enqueue`: inserir no final.

\- `dequeue`: remover do início.

\- `front`: consultar o primeiro.



Em Python, podemos simular usando `collections.deque` para performance.



```python

from collections import deque



fila = deque()

fila.append("João")    # enqueue

fila.append("Maria")

fila.append("José")

print(fila.popleft())  # João (primeiro a entrar)

print(fila\[0])         # front: Maria

```



Aplicações: gerenciamento de processos, filas de impressão, simulações.



\### 7.4 Comparativo rápido



| Estrutura | Ordem de saída | Inserção | Remoção |

|-----------|----------------|----------|---------|

| Lista      | Qualquer (índice) | Fim ou posição | Fim ou posição |

| Pilha      | LIFO           | Topo         | Topo |

| Fila       | FIFO           | Final        | Início |



> \*\*Desafio:\*\* Dada a sequência de operações: push 1, push 2, pop, push 3, pop, pop em uma pilha inicialmente vazia, qual a ordem dos elementos removidos? Repita o mesmo raciocínio para uma fila.



\---



\## 8. Noções de complexidade de algoritmos



Nem todos os programas são igualmente eficientes. A \*\*complexidade\*\* mede como o consumo de recursos (tempo, memória) cresce conforme o tamanho da entrada aumenta. A notação mais comum é o \*\*Big O\*\*, que descreve o pior caso.



\### 8.1 Notação Big O



Ela foca no termo dominante, ignorando constantes. Exemplos:



\- `O(1)`: tempo constante. Exemplo: acessar um elemento de lista por índice.

\- `O(log n)`: crescimento logarítmico. Exemplo: busca binária em lista ordenada.

\- `O(n)`: linear. Exemplo: percorrer uma lista de tamanho `n`.

\- `O(n log n)`: log-linear. Exemplo: algoritmos eficientes de ordenação (merge sort).

\- `O(n²)`: quadrático. Exemplo: dois laços aninhados percorrendo a mesma lista.

\- `O(2ⁿ)`: exponencial. Exemplo: Fibonacci recursivo ingênuo.



\### 8.2 Analisando exemplos simples



\*\*Busca linear em lista não ordenada:\*\*

```python

def busca(lista, valor):

&#x20;   for elemento in lista:

&#x20;       if elemento == valor:

&#x20;           return True

&#x20;   return False

```

No pior caso, visitamos todos os `n` elementos → `O(n)`.



\*\*Soma de todos os pares (laços aninhados):\*\*

```python

def todos\_pares(lista):

&#x20;   n = len(lista)

&#x20;   for i in range(n):

&#x20;       for j in range(n):

&#x20;           print(lista\[i] + lista\[j])

```

Para cada `i` (n iterações), fazemos `n` iterações de `j` → `O(n²)`.



\*\*Recursão do Fibonacci:\*\*

Cada chamada gera duas novas chamadas, a árvore tem profundidade `n` e aproximadamente `2ⁿ` nós → `O(2ⁿ)`. Por isso é lento para `n=40`.



\### 8.3 Por que se preocupar com complexidade?



Imagine duas soluções para o mesmo problema: uma `O(n²)` e outra `O(n log n)`. Se `n = 1.000.000`, a primeira fará cerca de 1 trilhão de operações, enquanto a segunda na casa de 20 milhões – a diferença entre minutos e segundos.



\*\*Dica:\*\* Sempre procure reduzir o número de laços aninhados e, se possível, usar estruturas como dicionários (tabelas hash) que oferecem buscas em `O(1)` (em média).



> \*\*Desafio:\*\* Analise a complexidade da função `fatorial` recursiva. Qual a sua Big O em termos de multiplicações realizadas?



\---



\## 9. Integrando os conceitos: um exemplo completo



Vamos construir um pequeno sistema de controle de atendimento em um consultório, usando fila, funções e condicionais.



```python

from collections import deque



def adicionar\_paciente(fila, nome, prioridade=False):

&#x20;   if prioridade:

&#x20;       # simplicidade: coloca no início da fila (não é FIFO puro)

&#x20;       fila.appendleft(nome)

&#x20;   else:

&#x20;       fila.append(nome)

&#x20;   print(f"Paciente {nome} adicionado.")



def chamar\_proximo(fila):

&#x20;   if len(fila) == 0:

&#x20;       print("Nenhum paciente aguardando.")

&#x20;   else:

&#x20;       paciente = fila.popleft()

&#x20;       print(f"Chamando {paciente}.")



\# programa principal

fila\_atendimento = deque()

adicionar\_paciente(fila\_atendimento, "Ana")

adicionar\_paciente(fila\_atendimento, "Bruno")

adicionar\_paciente(fila\_atendimento, "Carla", prioridade=True)

chamar\_proximo()  # Carla (prioridade)

chamar\_proximo()  # Ana

chamar\_proximo()  # Bruno

chamar\_proximo()  # vazia

```



Nesse exemplo aparecem: variáveis, estruturas de dados (deque como fila com prioridade simplificada), condicionais, funções e laços (implícitos nos métodos da deque).



\---



\## 10. Conclusão e próximos passos



Você acabou de percorrer os pilares da lógica de programação:



\- \*\*Variáveis e tipos\*\* dão forma aos dados.

\- \*\*Operadores\*\* permitem cálculos e comparações.

\- \*\*Estruturas de controle\*\* definem o fluxo do programa.

\- \*\*Funções\*\* organizam e reutilizam código.

\- \*\*Recursão\*\* resolve problemas de forma elegante, com cuidados de desempenho.

\- \*\*Estruturas de dados\*\* (listas, pilhas, filas) modelam o armazenamento.

\- \*\*Complexidade\*\* ajuda a avaliar e melhorar seus algoritmos.



Esses conceitos são a base para aprender qualquer linguagem, desenvolver aplicações reais e avançar para tópicos como algoritmos de ordenação, estruturas de dados avançadas, programação orientada a objetos e muito mais.



Pratique resolvendo pequenos problemas, implemente as ideias em papel ou no computador e, acima de tudo, divirta-se com a lógica. Bons códigos!



\---



\*\*Desafios finais:\*\*

1\. Escreva uma função que receba uma lista de números e retorne o maior elemento (sem usar funções prontas).

2\. Crie uma função recursiva para inverter uma string.

3\. Modele uma pilha de livros e simule as operações de empilhar e desempilhar, imprimindo o estado a cada passo.

4\. Dado um algoritmo que possui um laço que vai até `n` e dentro dele outro laço que vai até `10`, qual a complexidade total? (cuidado com as constantes!)

```



\*\*Nota:\*\* O conteúdo foi projetado para ser independente, didático e pronto para ser convertido em páginas web (basta adicionar o markdown gerado a um gerador de sites estáticos ou a uma aplicação que renderize MD). Inclui uma progressão lógica, exemplos comentados, desafios interativos e resumos que facilitam a fixação.

