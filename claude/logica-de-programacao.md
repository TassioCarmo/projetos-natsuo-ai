# Lógica de Programação: Do Zero à Complexidade

> Um guia completo e didático para quem quer entender como o computador pensa — e como você pode pensar como um programador.

---

## Sumário

1. [O que é Lógica de Programação?](#o-que-é-lógica-de-programação)
2. [Variáveis e Constantes](#variáveis-e-constantes)
3. [Tipos de Dados](#tipos-de-dados)
4. [Operadores](#operadores)
5. [Estruturas de Controle](#estruturas-de-controle)
   - [Condicionais](#condicionais)
   - [Laços de Repetição](#laços-de-repetição)
6. [Funções](#funções)
7. [Recursão](#recursão)
8. [Estruturas de Dados Básicas](#estruturas-de-dados-básicas)
   - [Arrays (Vetores)](#arrays-vetores)
   - [Pilhas e Filas](#pilhas-e-filas)
   - [Dicionários (Mapas)](#dicionários-mapas)
9. [Noções de Complexidade](#noções-de-complexidade)
10. [Conclusão](#conclusão)

---

## O que é Lógica de Programação?

Antes de escrever qualquer linha de código, é preciso entender o que você está fazendo: **dar instruções precisas a uma máquina que não tem intuição**.

Um computador é incrivelmente rápido, mas literalmente burro. Ele executa exatamente o que você mandar, nem mais, nem menos. Isso significa que **a clareza do seu raciocínio é mais importante do que qualquer linguagem de programação**.

> 💡 **Analogia:** Pense em uma receita de bolo. Você não diz "coloque farinha suficiente" — você diz "coloque 200g de farinha". Lógica de programação é a arte de transformar intenções vagas em instruções exatas e ordenadas.

A lógica de programação é a base que sustenta tudo. Ela não pertence a nenhuma linguagem específica. Aprenda-a bem e você será capaz de aprender qualquer linguagem com facilidade.

Os exemplos neste guia serão escritos em **pseudocódigo** e em **Python**, por ser uma linguagem limpa e próxima do português natural.

---

## Variáveis e Constantes

Uma **variável** é um nome que aponta para um espaço na memória do computador onde você guarda um valor. Pense nela como uma caixinha com um rótulo.

```python
idade = 25
nome = "Maria"
altura = 1.68
esta_chovendo = True
```

O valor de uma variável pode mudar ao longo do programa — daí o nome *variável*:

```python
pontuacao = 0
pontuacao = pontuacao + 10   # agora vale 10
pontuacao = pontuacao + 5    # agora vale 15
```

Uma **constante** é um valor que não deve mudar durante a execução. Em Python, não há constante "oficial", mas a convenção é escrever em maiúsculas para sinalizar essa intenção:

```python
PI = 3.14159
VELOCIDADE_DA_LUZ = 299_792_458  # m/s
TAXA_DE_JUROS = 0.05
```

### Boas práticas ao nomear variáveis

| ❌ Evite | ✅ Prefira |
|---|---|
| `x` | `velocidade_inicial` |
| `d` | `data_nascimento` |
| `temp2` | `temperatura_media` |
| `varAuxiliar3` | `total_desconto` |

> O código é lido muito mais vezes do que é escrito. Nomear bem uma variável é um ato de respeito com quem vai ler depois — inclusive você mesmo no futuro.

---

## Tipos de Dados

Todo valor tem um **tipo**, que determina o que você pode fazer com ele. Somar dois números é diferente de juntar duas palavras.

### Tipos Primitivos

| Tipo | Descrição | Exemplo |
|---|---|---|
| `int` | Número inteiro | `42`, `-7`, `0` |
| `float` | Número decimal | `3.14`, `-0.5`, `2.0` |
| `str` | Texto (string) | `"olá"`, `"Python"` |
| `bool` | Verdadeiro ou Falso | `True`, `False` |

```python
# Inteiros: operações exatas
filhos = 3
ano = 2024

# Floats: representação de frações
preco = 19.99
temperatura = -3.5

# Strings: texto entre aspas
cidade = "São Paulo"
mensagem = 'Olá, mundo!'

# Booleans: só dois valores possíveis
logado = True
admin = False
```

### Tipagem Dinâmica vs. Estática

Python é **dinamicamente tipado**: você não precisa declarar o tipo, ele é inferido pelo valor. Já linguagens como Java ou C são **estaticamente tipadas**: você precisa declarar o tipo explicitamente.

```python
# Python (dinâmico)
x = 10       # x é int
x = "dez"   # agora x é str — válido!
```

```java
// Java (estático)
int x = 10;
x = "dez";  // ERRO de compilação!
```

### Conversão de Tipos (Type Casting)

Às vezes você precisa converter um tipo em outro:

```python
# Usuário digita um texto, mas você precisa do número
entrada = input("Qual sua idade? ")  # entrada é str
idade = int(entrada)                 # converte para int

# Converter número para texto
codigo = 42
mensagem = "Seu código é: " + str(codigo)

# Cuidado com conversões inválidas!
valor = int("abc")  # Erro! "abc" não é um número
```

---

## Operadores

Operadores são os **verbos** da lógica: eles realizam ações sobre os dados.

### Operadores Aritméticos

```python
a = 10
b = 3

print(a + b)   # 13  → adição
print(a - b)   # 7   → subtração
print(a * b)   # 30  → multiplicação
print(a / b)   # 3.333... → divisão real
print(a // b)  # 3   → divisão inteira (quociente)
print(a % b)   # 1   → módulo (resto da divisão)
print(a ** b)  # 1000 → potenciação
```

> 💡 **O operador módulo `%` é muito útil!** Ele responde: "qual o resto quando divido `a` por `b`?" Use-o para saber se um número é par (`n % 2 == 0`), para criar ciclos, ou para "embrulhar" índices.

### Operadores de Comparação

Sempre retornam `True` ou `False`:

```python
10 > 5    # True
10 < 5    # False
10 == 10  # True  (igual)
10 != 7   # True  (diferente)
10 >= 10  # True  (maior ou igual)
5 <= 3    # False (menor ou igual)
```

### Operadores Lógicos

Combinam condições:

```python
# AND: ambas precisam ser True
idade = 20
tem_carteira = True
pode_dirigir = (idade >= 18) and tem_carteira  # True

# OR: pelo menos uma precisa ser True
tem_dinheiro = False
tem_cartao = True
pode_pagar = tem_dinheiro or tem_cartao  # True

# NOT: inverte o valor
esta_fechado = False
esta_aberto = not esta_fechado  # True
```

---

## Estruturas de Controle

Por padrão, um programa executa linha por linha, de cima para baixo. As estruturas de controle permitem **desviar esse fluxo**: tomar decisões e repetir ações.

---

### Condicionais

#### `if`, `elif`, `else`

A estrutura condicional básica: **"se isso, faça aquilo; senão, faça outra coisa"**.

```python
temperatura = 38.5

if temperatura > 39:
    print("Febre alta! Vá ao médico.")
elif temperatura > 37.5:
    print("Febre moderada. Descanse e tome água.")
elif temperatura > 36:
    print("Temperatura normal.")
else:
    print("Temperatura abaixo do normal. Agasalhe-se.")
```

**Como o computador lê isso:**
1. Testa a primeira condição. Se for verdadeira, executa o bloco e **pula todo o resto**.
2. Se for falsa, testa a próxima condição (`elif`).
3. Se nenhuma condição for verdadeira, executa o `else`.

#### Condicionais Aninhadas

Você pode colocar um `if` dentro de outro:

```python
nota = 7.5
frequencia = 80

if frequencia >= 75:
    if nota >= 7:
        print("Aprovado!")
    elif nota >= 5:
        print("Recuperação.")
    else:
        print("Reprovado por nota.")
else:
    print("Reprovado por falta.")
```

> ⚠️ **Atenção:** condicionais muito aninhadas dificultam a leitura. Quando perceber que está indo fundo demais, pense em reestruturar seu código com funções.

---

### Laços de Repetição

#### `while` — repete enquanto uma condição for verdadeira

```python
contador = 1

while contador <= 5:
    print(f"Contagem: {contador}")
    contador = contador + 1

# Saída:
# Contagem: 1
# Contagem: 2
# Contagem: 3
# Contagem: 4
# Contagem: 5
```

Use `while` quando **você não sabe de antemão quantas repetições** serão necessárias:

```python
senha_correta = "python123"
tentativas = 0

while True:
    senha = input("Digite sua senha: ")
    tentativas += 1

    if senha == senha_correta:
        print(f"Acesso liberado após {tentativas} tentativa(s).")
        break  # sai do laço
    else:
        print("Senha incorreta. Tente novamente.")
```

#### `for` — repete para cada item de uma sequência

```python
frutas = ["maçã", "banana", "laranja", "uva"]

for fruta in frutas:
    print(f"Eu gosto de {fruta}.")
```

Usando `range()` para repetir um número fixo de vezes:

```python
# range(5) gera: 0, 1, 2, 3, 4
for i in range(5):
    print(i)

# range(início, fim, passo)
for i in range(1, 11, 2):
    print(i)  # 1, 3, 5, 7, 9
```

#### `break` e `continue`

- **`break`**: interrompe o laço imediatamente.
- **`continue`**: pula para a próxima iteração, ignorando o restante do bloco.

```python
# Encontrar o primeiro número par em uma lista
numeros = [7, 3, 11, 4, 9, 2]

for n in numeros:
    if n % 2 == 0:
        print(f"Primeiro par encontrado: {n}")
        break

# Imprimir apenas números ímpares
for n in range(10):
    if n % 2 == 0:
        continue  # pula os pares
    print(n)  # 1, 3, 5, 7, 9
```

#### Exemplo completo: tabuada

```python
numero = 7

print(f"Tabuada do {numero}:")
for i in range(1, 11):
    resultado = numero * i
    print(f"{numero} x {i:2d} = {resultado:3d}")
```

---

## Funções

Uma função é um **bloco de código nomeado** que realiza uma tarefa específica e pode ser reutilizado.

> 💡 **Por que usar funções?**
> - **Reutilização:** escreva uma vez, use várias vezes.
> - **Organização:** divida o problema em partes menores.
> - **Legibilidade:** código com funções bem nomeadas se lê quase como texto.
> - **Manutenção:** para corrigir um bug, basta alterar em um único lugar.

### Anatomia de uma Função

```python
def calcular_media(nota1, nota2, nota3):
    """
    Calcula a média aritmética de três notas.
    Parâmetros: nota1, nota2, nota3 (float)
    Retorna: a média (float)
    """
    soma = nota1 + nota2 + nota3
    media = soma / 3
    return media

# Chamando a função:
resultado = calcular_media(8.0, 7.5, 9.0)
print(f"Média: {resultado:.2f}")  # Média: 8.17
```

### Parâmetros e Argumentos

**Parâmetro** é o nome na definição da função. **Argumento** é o valor que você passa ao chamar:

```python
def saudar(nome, saudacao="Olá"):  # "saudacao" tem valor padrão
    return f"{saudacao}, {nome}!"

print(saudar("Ana"))              # Olá, Ana!
print(saudar("Carlos", "Oi"))    # Oi, Carlos!
print(saudar("Bia", "Bom dia"))  # Bom dia, Bia!
```

### Escopo de Variáveis

Variáveis criadas dentro de uma função **não existem fora dela**:

```python
def calcular():
    resultado = 42  # variável LOCAL
    return resultado

calcular()
print(resultado)  # Erro! 'resultado' não existe aqui fora
```

Isso é uma coisa boa: funções são **caixas pretas** que recebem entradas e produzem saídas, sem interferir no resto do programa.

### Múltiplos Retornos

```python
def dividir(dividendo, divisor):
    if divisor == 0:
        return None, "Erro: divisão por zero"
    quociente = dividendo // divisor
    resto = dividendo % divisor
    return quociente, resto

q, r = dividir(17, 5)
print(f"17 ÷ 5 = {q} com resto {r}")  # 17 ÷ 5 = 3 com resto 2
```

### Exemplo prático: validador de senha

```python
def validar_senha(senha):
    """Verifica se a senha atende aos critérios de segurança."""
    if len(senha) < 8:
        return False, "Senha muito curta (mínimo 8 caracteres)"

    tem_numero = any(c.isdigit() for c in senha)
    if not tem_numero:
        return False, "Senha deve conter pelo menos um número"

    tem_maiuscula = any(c.isupper() for c in senha)
    if not tem_maiuscula:
        return False, "Senha deve conter pelo menos uma letra maiúscula"

    return True, "Senha válida!"


# Testando
senhas = ["abc", "minhasenha", "MinhaSenha1"]

for s in senhas:
    valida, mensagem = validar_senha(s)
    status = "✓" if valida else "✗"
    print(f"{status} '{s}': {mensagem}")
```

---

## Recursão

Recursão é quando uma função **chama a si mesma** para resolver um problema. É uma técnica elegante para problemas que têm **estrutura repetitiva ou autossimilar**.

> 💡 **Analogia:** Pense em dois espelhos paralelos. A imagem de você dentro do espelho contém outro espelho que contém outra imagem sua... Isso é recursão — mas precisamos de um jeito de parar!

Toda função recursiva tem dois componentes obrigatórios:
1. **Caso base:** a condição de parada (sem ela, recursão infinita = travamento).
2. **Caso recursivo:** a função chamando a si mesma com uma entrada *menor*.

### Exemplo 1: Fatorial

O fatorial de `n` (escrito `n!`) é definido como:
- `0! = 1` (caso base)
- `n! = n × (n-1)!` (caso recursivo)

```python
def fatorial(n):
    # Caso base
    if n == 0:
        return 1
    # Caso recursivo
    return n * fatorial(n - 1)

print(fatorial(5))  # 120
```

**Visualizando as chamadas:**

```
fatorial(5)
  = 5 * fatorial(4)
        = 4 * fatorial(3)
              = 3 * fatorial(2)
                    = 2 * fatorial(1)
                          = 1 * fatorial(0)
                                = 1  ← caso base!
                          = 1 * 1 = 1
                    = 2 * 1 = 2
              = 3 * 2 = 6
        = 4 * 6 = 24
  = 5 * 24 = 120
```

### Exemplo 2: Sequência de Fibonacci

Fibonacci é definido como:
- `fib(0) = 0`, `fib(1) = 1` (casos base)
- `fib(n) = fib(n-1) + fib(n-2)` (caso recursivo)

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)

for i in range(10):
    print(fibonacci(i), end=" ")
# 0 1 1 2 3 5 8 13 21 34
```

### Recursão vs. Iteração

Ambas resolvem o mesmo problema, mas de formas diferentes:

```python
# Fatorial iterativo
def fatorial_iterativo(n):
    resultado = 1
    for i in range(2, n + 1):
        resultado *= i
    return resultado

# Fatorial recursivo
def fatorial_recursivo(n):
    if n == 0:
        return 1
    return n * fatorial_recursivo(n - 1)
```

| | Iteração | Recursão |
|---|---|---|
| **Velocidade** | Geralmente mais rápida | Pode ser mais lenta |
| **Memória** | Usa menos memória | Cada chamada usa a pilha de execução |
| **Legibilidade** | Mais verbosa às vezes | Mais elegante para certos problemas |
| **Risco** | Laço infinito | Stack overflow (recursão infinita) |

> 🔑 **Quando usar recursão?** Quando o problema for naturalmente dividido em subproblemas menores do mesmo tipo — como navegar em árvores, busca binária, e algoritmos de divisão e conquista (merge sort, quicksort).

---

## Estruturas de Dados Básicas

Estruturas de dados são **formas de organizar e armazenar informações** para que possam ser acessadas e modificadas eficientemente.

---

### Arrays (Vetores)

Um array é uma **coleção ordenada de elementos do mesmo tipo** (em linguagens como C/Java) ou de tipos mistos (em Python, chamado de `list`). O acesso é feito por **índice** (posição), começando em 0.

```
Índice:   0      1       2       3       4
Valor:  ["Ana", "Bia", "Carlos", "Davi", "Eva"]
```

```python
alunos = ["Ana", "Bia", "Carlos", "Davi", "Eva"]

print(alunos[0])    # "Ana"  (primeiro elemento)
print(alunos[-1])   # "Eva"  (último elemento)
print(alunos[1:3])  # ["Bia", "Carlos"] (fatiamento)

# Modificar
alunos[2] = "Carla"

# Adicionar ao final
alunos.append("Felipe")

# Remover
alunos.remove("Bia")

# Tamanho
print(len(alunos))
```

#### Iterando sobre arrays

```python
notas = [7.5, 8.0, 6.5, 9.0, 7.0]

# Calcular média
soma = 0
for nota in notas:
    soma += nota
media = soma / len(notas)
print(f"Média: {media:.2f}")  # Média: 7.60

# Encontrar a maior nota
maior = notas[0]
for nota in notas:
    if nota > maior:
        maior = nota
print(f"Maior nota: {maior}")  # Maior nota: 9.0
```

#### Arrays bidimensionais (matrizes)

```python
# Matriz 3x3
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

print(matriz[1][2])  # 6 (linha 1, coluna 2)

# Percorrer a matriz inteira
for linha in matriz:
    for elemento in linha:
        print(elemento, end=" ")
    print()  # nova linha
```

---

### Pilhas e Filas

Duas estruturas essenciais que diferem na **ordem de remoção dos elementos**.

#### Pilha (Stack) — LIFO: Last In, First Out

O último a entrar é o primeiro a sair. Pense em uma pilha de pratos: você só retira o do topo.

```
Empilha (push): →  [ ]  →  [A]  →  [A,B]  →  [A,B,C]
Desempilha (pop):  [A,B,C] → [A,B] → [A] → [ ]
```

```python
pilha = []

# push: adicionar no topo
pilha.append("A")
pilha.append("B")
pilha.append("C")
print(pilha)  # ['A', 'B', 'C']

# pop: remover do topo
topo = pilha.pop()
print(topo)   # 'C'
print(pilha)  # ['A', 'B']
```

**Casos de uso reais:**
- Histórico de undo/redo em editores de texto
- Chamadas de função (call stack)
- Validação de parênteses balanceados

```python
def parenteses_balanceados(expressao):
    """Verifica se parênteses, colchetes e chaves estão balanceados."""
    pilha = []
    pares = {')': '(', ']': '[', '}': '{'}

    for char in expressao:
        if char in '([{':
            pilha.append(char)
        elif char in ')]}':
            if not pilha or pilha[-1] != pares[char]:
                return False
            pilha.pop()

    return len(pilha) == 0

print(parenteses_balanceados("(a + b) * [c - d]"))  # True
print(parenteses_balanceados("(a + [b)"))            # False
```

---

#### Fila (Queue) — FIFO: First In, First Out

O primeiro a entrar é o primeiro a sair. Pense em uma fila de banco.

```
Enfileira (enqueue): →  [ ]  →  [A]  →  [A,B]  →  [A,B,C]
Desenfileira (dequeue):  [A,B,C] → [B,C] → [C] → [ ]
                           ↑ remove sempre do início
```

```python
from collections import deque

fila = deque()

# enqueue
fila.append("João")
fila.append("Maria")
fila.append("Pedro")
print(fila)  # deque(['João', 'Maria', 'Pedro'])

# dequeue
proximo = fila.popleft()
print(proximo)  # 'João'
print(fila)     # deque(['Maria', 'Pedro'])
```

**Casos de uso reais:**
- Fila de impressão
- Gerenciamento de requisições em servidores
- Algoritmos de busca em largura (BFS)

---

### Dicionários (Mapas)

Um dicionário armazena pares de **chave → valor**. Em vez de acessar por posição (índice), você acessa pelo nome (chave). É como um dicionário real: você procura a palavra e obtém a definição.

```python
aluno = {
    "nome": "Lucas",
    "idade": 20,
    "notas": [8.5, 9.0, 7.5],
    "aprovado": True
}

# Acessar
print(aluno["nome"])     # "Lucas"
print(aluno["idade"])    # 20

# Modificar
aluno["idade"] = 21

# Adicionar nova chave
aluno["email"] = "lucas@email.com"

# Verificar se chave existe
if "telefone" in aluno:
    print(aluno["telefone"])
else:
    print("Telefone não cadastrado")

# Valor padrão se chave não existir
cidade = aluno.get("cidade", "Não informado")
```

#### Iterando sobre dicionários

```python
estoque = {
    "maçã": 150,
    "banana": 80,
    "laranja": 200,
    "uva": 45
}

# Iterar sobre chaves e valores
for produto, quantidade in estoque.items():
    if quantidade < 100:
        print(f"⚠️  {produto}: apenas {quantidade} unidades")

# Contar total
total = sum(estoque.values())
print(f"Total em estoque: {total} unidades")
```

#### Frequência de palavras (uso clássico de dicionários)

```python
def contar_palavras(texto):
    palavras = texto.lower().split()
    frequencia = {}

    for palavra in palavras:
        if palavra in frequencia:
            frequencia[palavra] += 1
        else:
            frequencia[palavra] = 1

    return frequencia

texto = "o gato viu o rato e o rato fugiu do gato"
contagem = contar_palavras(texto)

for palavra, count in sorted(contagem.items(), key=lambda x: -x[1]):
    print(f"'{palavra}': {count}x")
```

---

## Noções de Complexidade

Quando você escreve um algoritmo, duas perguntas são fundamentais:
- **Quão rápido ele é?** → Complexidade de **tempo**
- **Quanta memória usa?** → Complexidade de **espaço**

A **notação Big O** descreve como o desempenho do algoritmo cresce à medida que a entrada cresce. Ela foca no **pior caso** e ignora constantes e termos menores.

> 💡 **Imagine que `n` é o tamanho da sua entrada** — por exemplo, a quantidade de elementos em uma lista. Big O descreve o comportamento quando `n` fica muito grande.

### Principais Complexidades (da melhor para a pior)

| Notação | Nome | Exemplo |
|---|---|---|
| O(1) | Constante | Acessar `lista[i]` |
| O(log n) | Logarítmica | Busca binária |
| O(n) | Linear | Percorrer uma lista |
| O(n log n) | Linearítmica | Merge Sort |
| O(n²) | Quadrática | Bubble Sort, laços aninhados |
| O(2ⁿ) | Exponencial | Fibonacci recursivo ingênuo |

### O(1) — Constante

O tempo de execução **não depende do tamanho da entrada**. Sempre igualmente rápido.

```python
def primeiro_elemento(lista):
    return lista[0]  # sempre uma operação, independente do tamanho

# Acessa índice direto na memória — O(1)
```

### O(n) — Linear

O tempo cresce **proporcionalmente** ao tamanho da entrada.

```python
def busca_linear(lista, alvo):
    """Percorre a lista elemento por elemento."""
    for i in range(len(lista)):
        if lista[i] == alvo:
            return i  # encontrou
    return -1  # não encontrou

# Se a lista tem 100 elementos → até 100 operações
# Se a lista tem 1.000.000 elementos → até 1.000.000 operações
```

### O(log n) — Logarítmica

O tempo cresce muito devagar. Cada passo **divide o problema pela metade**.

```python
def busca_binaria(lista_ordenada, alvo):
    """Funciona apenas em listas ORDENADAS."""
    esquerda = 0
    direita = len(lista_ordenada) - 1

    while esquerda <= direita:
        meio = (esquerda + direita) // 2
        if lista_ordenada[meio] == alvo:
            return meio
        elif lista_ordenada[meio] < alvo:
            esquerda = meio + 1  # descarta metade esquerda
        else:
            direita = meio - 1   # descarta metade direita

    return -1
```

**Por que é O(log n)?**

```
Lista com 1.000.000 elementos:
Passo 1: busca em 1.000.000 elementos → verifica o do meio
Passo 2: busca em   500.000 elementos → verifica o do meio
Passo 3: busca em   250.000 elementos → verifica o do meio
...
Passo 20: busca em apenas 1 elemento → encontrou ou não!

log₂(1.000.000) ≈ 20 passos para 1 milhão de elementos!
```

### O(n²) — Quadrática

Geralmente surge de **laços aninhados**. Cuidado: escala muito mal.

```python
def bubble_sort(lista):
    """Ordena a lista por trocas repetidas."""
    n = len(lista)
    for i in range(n):          # O(n)
        for j in range(n - 1):  # O(n)   → total: O(n²)
            if lista[j] > lista[j + 1]:
                lista[j], lista[j + 1] = lista[j + 1], lista[j]
    return lista

# Com 100 elementos: ~10.000 operações
# Com 1.000 elementos: ~1.000.000 operações
# Com 10.000 elementos: ~100.000.000 operações (começa a ficar lento!)
```

### Comparação Visual

```
n = 10         n = 100        n = 1.000      n = 1.000.000
──────────────────────────────────────────────────────────
O(1):       1              1              1              1
O(log n):   3             7             10             20
O(n):      10           100          1.000      1.000.000
O(n log n): 30           700         10.000     20.000.000
O(n²):    100        10.000      1.000.000  1.000.000.000.000
O(2ⁿ):  1.024  1.267.650...  (astronomicamente grande)
```

> 🎯 **Regra prática:** Se você ver laços aninhados, suspeite de O(n²) ou pior. Se a entrada pode ser dividida ao meio repetidamente, provavelmente é O(log n) — e isso é ótimo.

### O problema do Fibonacci ingênuo

Voltando ao Fibonacci recursivo:

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)
```

Esse código é **O(2ⁿ)** porque cada chamada gera duas novas chamadas, e muitos subproblemas são recalculados repetidamente. Para `fibonacci(50)`, são trilhões de operações!

A solução é a **memoização**: guardar os resultados já calculados:

```python
def fibonacci_memo(n, memo={}):
    if n in memo:
        return memo[n]      # resultado já calculado: O(1)
    if n <= 1:
        return n
    memo[n] = fibonacci_memo(n - 1, memo) + fibonacci_memo(n - 2, memo)
    return memo[n]

# Agora é O(n) — cada valor calculado uma única vez!
print(fibonacci_memo(50))  # Instantâneo!
```

---

## Conclusão

Você percorreu o núcleo da lógica de programação:

| Conceito | O que faz |
|---|---|
| **Variáveis e Tipos** | Armazenam e classificam dados |
| **Operadores** | Manipulam e comparam dados |
| **Condicionais** | Tomam decisões |
| **Laços** | Repetem ações |
| **Funções** | Organizam e reutilizam código |
| **Recursão** | Resolvem problemas autossimilares |
| **Estruturas de Dados** | Organizam coleções de dados |
| **Complexidade** | Medem a eficiência de algoritmos |

Esses conceitos formam a **gramática universal da programação**. Toda linguagem — Python, JavaScript, Java, C++, Rust — os implementa de formas ligeiramente diferentes, mas a essência é sempre a mesma.

### Próximos Passos

O caminho natural após dominar esses fundamentos é:

1. **Orientação a Objetos** — modelar o mundo em classes e objetos
2. **Estruturas de Dados Avançadas** — árvores, grafos, heaps
3. **Algoritmos Clássicos** — ordenação, busca, grafos
4. **Paradigmas** — funcional, reativo, concorrente
5. **Sistemas** — memória, processos, redes

> *"Todo expert foi um dia um iniciante. A diferença é que o expert não desistiu quando ficou difícil."*

---

*Guia escrito com foco em clareza didática. Exemplos em Python 3.x.*
