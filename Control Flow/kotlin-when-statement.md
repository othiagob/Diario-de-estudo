# 🔍 Explorando o `when` em Kotlin: Estrutura de Decisão Poderosa

## 📌 Conceito Básico
O `when` em Kotlin é como um "supervisor inteligente" que analisa diferentes cenários e toma decisões baseado no tipo ou valor de uma variável. É similar ao `switch` de outras linguagens, mas muito mais flexível e expressivo.

## 🎯 Primeiro Exemplo: When Statement (Declaração)

### Código Completo
```kotlin
fun main() {
    cases("Hello")
    cases(1)
    cases(0L)
    cases(MyClass())
    cases("hello")
}

fun cases(obj: Any) {                                
    when (obj) {                                     
        1 -> println("One")                          
        "Hello" -> println("Greeting")               
        is Long -> println("Long")                   
        !is String -> println("Not a string")        
        else -> println("Unknown")                   
    }   
}
class MyClass
```

### 🧩 Análise Detalhada

#### Metáfora: O Controlador de Fluxo Versátil
Imagine o `when` como um "porteiro de eventos" em uma festa:
- Ele olha para cada convidado (objeto)
- Tem regras específicas para diferentes tipos de pessoas
- Se nenhuma regra se aplica, dá um tratamento padrão

#### Explicação Linha por Linha

1. `when (obj)`: Inicia a análise do objeto recebido
2. `1 -> println("One")`: Se o objeto for o número 1, imprime "One"
3. `"Hello" -> println("Greeting")`: Se for a string "Hello", imprime "Greeting"
4. `is Long -> println("Long")`: Se for um tipo Long, imprime "Long"
5. `!is String -> println("Not a string")`: Se NÃO for uma String, imprime "Not a string"
6. `else -> println("Unknown")`: Se nenhuma condição anterior for verdadeira, imprime "Unknown"

### 🚀 Exemplos Adicionais

#### Exemplo 1: Sistema de Pontuação de Jogador
```kotlin
fun playerStatus(points: Int) {
    when (points) {
        in 0..10 -> println("Iniciante")
        in 11..50 -> println("Intermediário")
        in 51..100 -> println("Avançado")
        else -> println("Mestre")
    }
}
```

#### Exemplo 2: Verificação de Tipo de Dado
```kotlin
fun analyzeData(data: Any) {
    when (data) {
        is Int -> println("Número inteiro detectado")
        is Double -> println("Número decimal detectado")
        is String -> println("Texto identificado")
        else -> println("Tipo desconhecido")
    }
}
```

## 🔬 Segundo Exemplo: When Expression (Expressão)

### Código Completo
```kotlin
fun main() {
    println(whenAssign("Hello"))
    println(whenAssign(3.4))
    println(whenAssign(1))
    println(whenAssign(MyClass()))
}

fun whenAssign(obj: Any): Any {
    val result = when (obj) {                   
        1 -> "one"                              
        "Hello" -> 1                            
        is Long -> false                        
        else -> 42                              
    }
    return result
}
class MyClass
```

### 🧩 Análise Detalhada

#### Metáfora: Máquina de Transformação
Pense no `when` como uma máquina que recebe um objeto e o transforma baseado em suas características.

#### Explicação Linha por Linha
1. `val result = when (obj)`: Cria uma variável que receberá o resultado da transformação
2. `1 -> "one"`: Se for 1, transforma em "one"
3. `"Hello" -> 1`: Se for "Hello", transforma em 1
4. `is Long -> false`: Se for Long, transforma em false
5. `else -> 42`: Se nenhuma condição anterior, transforma em 42

### 🚀 Exemplos Adicionais

#### Exemplo 1: Conversor de Moeda
```kotlin
fun convertCurrency(currency: String): Double {
    return when (currency) {
        "USD" -> 1.0
        "EUR" -> 0.85
        "BRL" -> 5.2
        else -> 0.0
    }
}
```

#### Exemplo 2: Calculadora de Desconto
```kotlin
fun calculateDiscount(customerType: String): Double {
    return when (customerType) {
        "GOLD" -> 0.2
        "SILVER" -> 0.1
        "BRONZE" -> 0.05
        else -> 0.0
    }
}
```

## 🔑 Principais Características
- Suporta múltiplos tipos de verificação
- Pode ser usado como declaração ou expressão
- Mais poderoso que o tradicional `switch`
- Permite verificações complexas de tipo e valor

## ⚠️ Boas Práticas
- Use `else` para cobrir casos não mapeados
- Prefira `when` a sequências longas de `if-else`
- Aproveite a versatilidade para códigos mais limpos

