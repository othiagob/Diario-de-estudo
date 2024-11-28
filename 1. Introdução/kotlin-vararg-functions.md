
# Funções com Parâmetros Vararg em Kotlin: Flexibilidade Argumentativa

## Introdução

Vararg (variable number of arguments) é um recurso poderoso em Kotlin que permite criar funções capazes de aceitar um número indefinido de argumentos do mesmo tipo. É como dar à sua função a capacidade de ser um recipiente elástico que se expande conforme necessário.

## Código de Referência

```kotlin
fun printAll(vararg messages: String) {                            
    for (m in messages) println(m)
}
printAll("Hello", "Hallo", "Salut", "Hola", "你好")                 

fun printAllWithPrefix(vararg messages: String, prefix: String) {  
    for (m in messages) println(prefix + m)
}
printAllWithPrefix(
    "Hello", "Hallo", "Salut", "Hola", "你好",
    prefix = "Greeting: "                                          
)

fun log(vararg entries: String) {
    printAll(*entries)                                             
}
log("Hello", "Hallo", "Salut", "Hola", "你好")
```

## Anatomia das Funções Vararg

### Características Fundamentais

- Permite passar número variável de argumentos
- Representa uma matriz (array) internamente
- Pode ser o último ou único parâmetro da função
- Sintaxe: `vararg nomeDoParametro: Tipo`

## Exemplos Detalhados

### 1. Função Básica de Impressão

```kotlin
fun printAll(vararg messages: String) {
    for (m in messages) println(m)
}

// Chamadas possíveis:
printAll("Olá")
printAll("Bom dia", "Boa tarde", "Boa noite")
printAll()  // Função também aceita zero argumentos
```

**Mecânica Interna**:
- `messages` se comporta como um array de Strings
- Pode receber zero, um ou múltiplos argumentos
- Itera sobre todos os argumentos passados

**Analogia**: 
Como um megafone que pode amplificar de um a múltiplos sons simultaneamente.

### 2. Função com Prefixo Adicional

```kotlin
fun printAllWithPrefix(vararg messages: String, prefix: String) {
    for (m in messages) println(prefix + m)
}

// Chamada:
printAllWithPrefix("Hello", "World", prefix = "Greeting: ")
```

**Características Especiais**:
- Vararg não precisa ser o último parâmetro
- Argumentos nomeados permitem flexibilidade
- Prefixo pode ser definido de forma independente

**Analogia**:
Como um carimbo que pode ser aplicado em diferentes documentos.

### 3. Espalhamento de Argumentos

```kotlin
fun log(vararg entries: String) {
    printAll(*entries)  // Operador spread (*)
}
```

**Operador Spread (`*`)**:
- Permite passar um array como argumentos vararg
- "Desempacota" o array para argumentos individuais
- Facilita passar arrays para funções vararg

**Analogia**:
Como um desdobrador mágico que transforma uma mala fechada em itens separados.

## Casos de Uso Avançados

### Função de Soma Genérica

```kotlin
fun <T extends Number> sum(vararg numbers: T): Double {
    return numbers.sumOf { it.toDouble() }
}

fun main() {
    println(sum(1, 2, 3, 4, 5))           // Inteiros
    println(sum(1.5, 2.7, 3.2))           // Doubles
}
```

### Construtor de Mensagens

```kotlin
fun createMessage(vararg parts: String, separator: String = " "): String {
    return parts.joinToString(separator)
}

fun main() {
    println(createMessage("Kotlin", "é", "incrível"))
    println(createMessage("Dados", "separados", "por", separator = "-"))
}
```

## Boas Práticas

1. Use quando número de argumentos for variável
2. Evite sobrecarregar com muitos parâmetros
3. Prefira listas ou arrays para coleções grandes
4. Documente claramente o uso esperado

## Considerações Importantes

- Performance pode ser menor que arrays pré-definidos
- Cuidado com funções com muitos parâmetros vararg
- Legibilidade deve ser prioridade

## Desafio Mental 🧠

Reflita:
- Como você usaria vararg para criar uma função de log?
- Que outros usos criativos você pode imaginar?

## Metáfora Final 🎭

Funções vararg são como um ônibus elástico: podem acomodar poucos ou muitos passageiros, sempre se adaptando às necessidades do momento.

