# Valores de Parâmetros Padrão e Argumentos Nomeados em Kotlin

## Introdução

Kotlin oferece recursos poderosos para definição de funções, permitindo maior flexibilidade e legibilidade no código através de valores de parâmetros padrão e argumentos nomeados.

## Código de Referência

```kotlin
fun printMessage(message: String): Unit {
    println(message)
}

fun printMessageWithPrefix(message: String, prefix: String = "Info") {
    println("[$prefix] $message")
}

fun sum(x: Int, y: Int): Int {
    return x + y
}

fun multiply(x: Int, y: Int) = x * y

fun main() {
    printMessage("Hello")                                   
    printMessageWithPrefix("Hello", "Log")                  
    printMessageWithPrefix("Hello")                         
    printMessageWithPrefix(prefix = "Log", message = "Hello")
    println(sum(1, 2))                                      
    println(multiply(2, 4))                                 
}
```

## Análise Detalhada das Funções

### 1. Função `printMessage()`

#### Características
- Recebe um parâmetro `message` do tipo `String`
- Retorna `Unit` (equivalente a `void`)
- Imprime a mensagem diretamente

#### Exemplo de Uso
```kotlin
printMessage("Olá, mundo!") // Imprime: Olá, mundo!
```

**Metáfora**: Como um mensageiro simples que entrega a mensagem sem modificações.

### 2. Função `printMessageWithPrefix()`

#### Características
- Dois parâmetros: `message` e `prefix`
- `prefix` possui valor padrão "Info"
- Imprime mensagem com prefixo entre colchetes

#### Exemplos de Uso
```kotlin
printMessageWithPrefix("Erro grave", "ALERT")  // Imprime: [ALERT] Erro grave
printMessageWithPrefix("Mensagem padrão")      // Imprime: [Info] Mensagem padrão
```

**Metáfora**: Como um carimbo que adiciona um selo informativo antes de cada mensagem.

### 3. Função `sum()`

#### Características
- Função tradicional com corpo de bloco
- Dois parâmetros inteiros
- Retorna a soma dos valores
- Utiliza palavra-chave `return`

#### Exemplo de Uso
```kotlin
val resultado = sum(5, 3)  // resultado = 8
```

**Metáfora**: Como um vendedor que soma dois valores e entrega o resultado final.

### 4. Função `multiply()`

#### Características
- Função de expressão única
- Sintaxe de atribuição direta
- Retorna produto de dois inteiros
- Mais concisa que funções tradicionais

#### Exemplo de Uso
```kotlin
val resultado = multiply(4, 5)  // resultado = 20
```

**Metáfora**: Como uma máquina de calcular que instantaneamente multiplica dois números.

## Exemplos Adicionais

### Exemplo 1: Função de Saudação Flexível

```kotlin
fun greet(name: String, greeting: String = "Olá", punctuation: String = "!") {
    println("$greeting, $name$punctuation")
}

fun main() {
    greet("Maria")                      // Olá, Maria!
    greet("João", "Bom dia")            // Bom dia, João!
    greet("Pedro", "Oi", ".")           // Oi, Pedro.
}
```

### Exemplo 2: Calculadora Versátil

```kotlin
fun calculate(
    x: Int, 
    y: Int, 
    operation: (Int, Int) -> Int = { a, b -> a + b }
) = operation(x, y)

fun main() {
    println(calculate(5, 3))                    // 8 (soma padrão)
    println(calculate(5, 3) { a, b -> a * b })  // 15 (multiplicação)
    println(calculate(10, 2) { a, b -> a / b }) // 5 (divisão)
}
```

## Pontos-Chave

- Valores padrão tornam funções mais flexíveis
- Argumentos nomeados melhoram legibilidade do código
- Kotlin permite sintaxes concisas e expressivas

## Conclusão

Os valores de parâmetros padrão e argumentos nomeados em Kotlin oferecem grande flexibilidade na definição e chamada de funções, permitindo códigos mais limpos, legíveis e versáteis.
