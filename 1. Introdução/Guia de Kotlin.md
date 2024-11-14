# Guia Detalhado de Fundamentos Kotlin

## Sumário
1. [Tipos de Dados, Operadores e Variáveis](#1-tipos-de-dados-operadores-e-variáveis)
2. [Trabalhando com Booleanos e Condições](#2-trabalhando-com-booleanos-e-condições)
3. [Entendendo Null Safety](#3-entendendo-null-safety)
4. [Arrays, Listas e Loops](#4-arrays-listas-e-loops)

## 1. Tipos de Dados, Operadores e Variáveis

### 1.1 Declarando Variáveis
Em Kotlin, temos duas formas principais de declarar variáveis:

```kotlin
// Usando 'val' - Imutável (não pode ser alterada)
val nome = "Maria"
// nome = "João" // Isso geraria um erro!

// Usando 'var' - Mutável (pode ser alterada)
var idade = 25
idade = 26 // Isso é permitido
```

**O que está acontecendo?**
- `val` cria uma variável que não pode ser alterada depois de inicializada (similar ao `final` em Java)
- `var` cria uma variável que pode ter seu valor modificado
- Kotlin usa inferência de tipos, então não precisamos declarar explicitamente o tipo

### 1.2 Tipos Numéricos
Kotlin oferece diversos tipos para representar números:

```kotlin
// Números inteiros
val pequeno: Byte = 127                    // 8 bits - Para números muito pequenos
val medio: Short = 32767                   // 16 bits - Para números médios
val normal: Int = 2147483647              // 32 bits - Tipo padrão para inteiros
val grande: Long = 9223372036854775807    // 64 bits - Para números muito grandes

// Números decimais
val altura: Float = 1.75f                  // 32 bits - Precisão de 6-7 dígitos
val peso: Double = 68.5                    // 64 bits - Precisão de 15-16 dígitos

// Conversões seguras
val numero = 10
val numeroLongo: Long = numero.toLong()    // Conversão explícita
```

**O que está acontecendo?**
- Cada tipo numérico tem um tamanho específico na memória
- Float requer 'f' no final para distinguir de Double
- Conversões entre tipos precisam ser explícitas para evitar perda de dados

### 1.3 Operadores Aritméticos e de Atribuição

```kotlin
// Operadores básicos
var a = 10
var b = 3

println(a + b)    // Adição: 13
println(a - b)    // Subtração: 7
println(a * b)    // Multiplicação: 30
println(a / b)    // Divisão: 3 (divisão inteira)
println(a % b)    // Módulo (resto): 1

// Operadores de atribuição compostos
var numero = 5
numero += 3       // numero = numero + 3
println(numero)   // 8
numero *= 2       // numero = numero * 2
println(numero)   // 16

// Incremento e decremento
var contador = 0
contador++        // Pós-incremento
++contador        // Pré-incremento
println(contador) // 2
```

**O que está acontecendo?**
- Operadores aritméticos funcionam como na matemática
- Operadores compostos (+=, -=, *=, /=) são atalhos para operações comuns
- Incremento/decremento pode ser antes (++x) ou depois (x++) da variável

## 2. Trabalhando com Booleanos e Condições

### 2.1 Expressões Booleanas

```kotlin
// Declaração de booleanos
val estaChovendo = true
val estaSol = false

// Operadores de comparação
val idade = 18
val ehMaior = idade >= 18        // true
val ehMenor = idade < 21         // true
val ehIgual = idade == 18        // true
val ehDiferente = idade != 20    // true

// Operadores lógicos
val temGuardaChuva = true
val deveSair = !estaChovendo || temGuardaChuva    // true (NOT + OR)
val podeIrPraia = estaSol && !estaChovendo        // false (AND)
```

**O que está acontecendo?**
- Booleanos só podem ter dois valores: `true` ou `false`
- Operadores de comparação retornam um booleano
- Operadores lógicos:
  - `!` (NOT) inverte o valor
  - `&&` (AND) só é true se ambos forem true
  - `||` (OR) é true se pelo menos um for true

### 2.2 Estruturas Condicionais

```kotlin
// If-else simples
val idade = 17
if (idade >= 18) {
    println("Pode dirigir")
} else {
    println("Não pode dirigir")
}

// If como expressão
val mensagem = if (idade >= 18) {
    "Maior de idade"
} else {
    "Menor de idade"
}

// When (substitui o switch de outras linguagens)
val diaDaSemana = 3
when (diaDaSemana) {
    1 -> println("Domingo")
    2 -> println("Segunda")
    3 -> println("Terça")
    4, 5 -> println("Meio da semana")
    in 6..7 -> println("Fim de semana")
    else -> println("Dia inválido")
}

// When como expressão
val tipoDia = when (diaDaSemana) {
    in 2..6 -> "Dia útil"
    else -> "Fim de semana"
}
```

**O que está acontecendo?**
- `if-else` avalia uma condição e executa um bloco de código
- Em Kotlin, `if` pode retornar um valor (ser uma expressão)
- `when` é mais poderoso que o `switch` tradicional:
  - Pode avaliar múltiplos valores por branch
  - Pode usar ranges (in 6..7)
  - Pode ser usado como expressão

## 3. Entendendo Null Safety

### 3.1 Tipos Nullable vs Non-Null

```kotlin
// Tipo não-nulo (padrão)
var nome: String = "Maria"
// nome = null // Isso causaria erro de compilação

// Tipo nullable (com ?)
var sobrenome: String? = "Silva"
sobrenome = null // Isso é permitido

// Operador safe call (?.)
val tamanho: Int? = sobrenome?.length // null se sobrenome for null

// Operador elvis (?:)
val comprimento: Int = sobrenome?.length ?: 0 // 0 se sobrenome for null

// Verificação de null
if (sobrenome != null) {
    println(sobrenome.length) // Smart cast - Kotlin sabe que não é null aqui
}

// Let com null safety
sobrenome?.let { nome ->
    println("Sobrenome tem ${nome.length} letras")
}
```

**O que está acontecendo?**
- Por padrão, variáveis não podem ser null
- Adicionar `?` após o tipo permite null
- `?.` (safe call) evita NullPointerException
- `?:` (elvis) fornece um valor padrão se for null
- Smart cast permite usar valor como non-null após verificação
- `let` executa um bloco apenas se o valor não for null

## 4. Arrays, Listas e Loops

### 4.1 Arrays e Listas

```kotlin
// Array de tamanho fixo
val numeros = Array(5) { it * 2 }  // [0, 2, 4, 6, 8]
println(numeros.joinToString())

// Lista imutável
val frutas = listOf("maçã", "banana", "laranja")
println(frutas[0])                 // maçã

// Lista mutável
val compras = mutableListOf("pão", "leite")
compras.add("queijo")              // Adiciona item
compras.removeAt(0)                // Remove primeiro item
println(compras)                   // [leite, queijo]

// Operações com listas
val numeros = listOf(1, 2, 3, 4, 5)
val dobrados = numeros.map { it * 2 }      // [2, 4, 6, 8, 10]
val pares = numeros.filter { it % 2 == 0 } // [2, 4]
```

**O que está acontecendo?**
- Arrays têm tamanho fixo após criação
- `listOf` cria lista imutável
- `mutableListOf` cria lista que pode ser modificada
- Listas têm métodos úteis como `map` e `filter`

### 4.2 Loops

```kotlin
// For com range
for (i in 1..5) {
    println(i) // Imprime 1, 2, 3, 4, 5
}

// For com until (exclui o último número)
for (i in 0 until 5) {
    println(i) // Imprime 0, 1, 2, 3, 4
}

// For com step
for (i in 0..10 step 2) {
    println(i) // Imprime 0, 2, 4, 6, 8, 10
}

// For com lista
val frutas = listOf("maçã", "banana", "laranja")
for (fruta in frutas) {
    println(fruta)
}

// While
var contador = 0
while (contador < 5) {
    println(contador)
    contador++
}

// Do-while
var numero = 1
do {
    println(numero)
    numero++
} while (numero <= 3)

// For com índice
for ((index, valor) in frutas.withIndex()) {
    println("$index: $valor")
}
```

**O que está acontecendo?**
- `1..5` cria um range inclusivo (1 até 5)
- `until` cria range exclusivo (não inclui o último)
- `step` define o incremento
- `for-in` itera sobre coleções
- `while` executa enquanto condição for verdadeira
- `do-while` executa pelo menos uma vez
- `withIndex()` permite acesso ao índice e valor

### Dicas de Boas Práticas

1. **Imutabilidade**: Prefira `val` sobre `var` quando possível
2. **Null Safety**: Use tipos nullable apenas quando necessário
3. **Smart Casts**: Aproveite as verificações de tipo do Kotlin
4. **Collections**: Prefira listas imutáveis quando não precisar modificar
5. **Expressividade**: Use when e if como expressões para código mais limpo

Este guia cobre os fundamentos essenciais do Kotlin com exemplos práticos e explicações detalhadas. Para aprofundar seu conhecimento, pratique os conceitos em projetos reais e consulte a documentação oficial do Kotlin.
