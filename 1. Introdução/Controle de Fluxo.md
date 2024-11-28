# Fluxo de Controle em Kotlin

## 1. WHEN

O `when` em Kotlin é uma estrutura de controle mais poderosa que o tradicional `switch` de outras linguagens. Pode ser usado como expressão (retornando valor) ou como instrução.

```kotlin
fun exemplosWhen() {
    // When básico
    val x = 1
    when (x) {
        1 -> println("x é 1")
        2 -> println("x é 2")
        else -> println("x não é nem 1 nem 2")
    }

    // When como expressão
    val str = when (x) {
        1 -> "Um"
        2 -> "Dois"
        else -> "Número diferente"
    }

    // When com múltiplos valores
    when (x) {
        0, 1 -> println("x é 0 ou 1")
        else -> println("x é outro número")
    }

    // When com ranges
    val y = 5
    when (y) {
        in 1..10 -> println("y está entre 1 e 10")
        !in 10..20 -> println("y não está entre 10 e 20")
        else -> println("nenhuma das anteriores")
    }

    // When com verificação de tipo
    val obj: Any = "Hello"
    when (obj) {
        is String -> println("É uma string de tamanho ${obj.length}")
        is Int -> println("É um número")
        else -> println("É outro tipo")
    }

    // When sem argumento
    val hora = 13
    when {
        hora < 12 -> println("Bom dia!")
        hora < 18 -> println("Boa tarde!")
        else -> println("Boa noite!")
    }
}
```

## 2. LOOPS

Kotlin oferece diferentes tipos de loops para iteração:

```kotlin
fun exemplosLoops() {
    // For loop básico com range
    for (i in 1..5) {
        println(i)
    }

    // For loop com step (passo)
    for (i in 0..10 step 2) {
        println(i) // Imprime números pares
    }

    // For loop decrescente
    for (i in 10 downTo 1) {
        println(i)
    }

    // For com collection
    val frutas = listOf("maçã", "banana", "laranja")
    for (fruta in frutas) {
        println(fruta)
    }

    // For com índice
    for ((index, value) in frutas.withIndex()) {
        println("$index: $value")
    }

    // While loop
    var x = 0
    while (x < 5) {
        println(x)
        x++
    }

    // Do-while loop
    var y = 0
    do {
        println(y)
        y++
    } while (y < 5)

    // Break e Continue
    for (i in 1..10) {
        if (i == 3) continue // Pula o 3
        if (i == 8) break    // Para no 8
        println(i)
    }
}
```

## 3. RANGES

Ranges em Kotlin são intervalos que podem ser criados para números ou caracteres:

```kotlin
fun exemplosRanges() {
    // Range numérico inclusivo
    val numeroRange = 1..10  // inclui 1 e 10

    // Range numérico exclusivo
    val numeroRangeExclusivo = 1 until 10  // inclui 1 mas não inclui 10

    // Range de caracteres
    val caracterRange = 'a'..'z'

    // Verificando se valor está no range
    println(5 in numeroRange)  // true
    println(11 in numeroRange) // false

    // Ranges decrescentes
    val rangeDecrescente = 10 downTo 1

    // Range com step
    val rangeComStep = 0..20 step 4

    // Iterando sobre ranges
    for (num in numeroRange) {
        println(num)
    }

    // Range com caracteres
    for (letra in 'A'..'F') {
        println(letra)
    }
}
```

## 4. EQUALITY CHECKS

Kotlin possui dois tipos de verificação de igualdade:

```kotlin
fun exemplosEqualityChecks() {
    // Igualdade estrutural (equals)
    val str1 = "Hello"
    val str2 = "Hello"
    println(str1 == str2)    // true (usa equals())
    println(str1.equals(str2)) // mesmo que acima

    // Igualdade referencial (mesma referência de objeto)
    println(str1 === str2)   // pode ser true devido ao string pool

    // Exemplo com objetos
    data class Pessoa(val nome: String, val idade: Int)
    
    val pessoa1 = Pessoa("João", 30)
    val pessoa2 = Pessoa("João", 30)
    val pessoa3 = pessoa1

    println(pessoa1 == pessoa2)   // true (igualdade estrutural)
    println(pessoa1 === pessoa2)  // false (referências diferentes)
    println(pessoa1 === pessoa3)  // true (mesma referência)

    // Null safety com igualdade
    val nullString: String? = null
    println(nullString == "hello")  // false
    println(nullString === "hello") // false
}
```

## 5. CONDITIONAL EXPRESSIONS

Kotlin oferece expressões condicionais poderosas:

```kotlin
fun exemplosConditionalExpressions() {
    // If como expressão
    val a = 5
    val b = 10
    val max = if (a > b) a else b

    // If com múltiplos blocos
    val resultado = if (a > b) {
        println("a é maior")
        a
    } else if (a < b) {
        println("b é maior")
        b
    } else {
        println("são iguais")
        a
    }

    // When como expressão
    val numero = 3
    val textoNumero = when (numero) {
        1 -> "um"
        2 -> "dois"
        3 -> "três"
        else -> "outro número"
    }

    // Elvis operator
    val nullableValue: String? = null
    val nonNullValue = nullableValue ?: "valor padrão"

    // Safe call com let
    nullableValue?.let {
        println("O valor não é null: $it")
    }

    // Try-catch como expressão
    val resultado2 = try {
        "123".toInt()
    } catch (e: NumberFormatException) {
        0
    }
}
```

## Características Importantes

1. Todas estas estruturas podem ser combinadas para criar lógicas mais complexas
2. Kotlin promove um código mais seguro com null-safety built-in
3. As expressões condicionais sempre retornam o último valor da expressão
4. O compilador garante que todas as condições possíveis sejam tratadas
5. A sintaxe é mais concisa que em muitas outras linguagens

### Exemplo Combinando Conceitos

```kotlin
fun exemploCombinado(input: Any?) {
    // Combinando when, null-safety, ranges e tipos
    val resultado = when {
        input == null -> "Input é null"
        input is Int && input in 1..100 -> "Número entre 1 e 100"
        input is String && input.length > 5 -> "String longa"
        input !is String && input !is Int -> "Tipo não suportado"
        else -> "Outro caso"
    }

    // Loop com conditional break
    for (i in 0..10) {
        val shouldContinue = when {
            i % 2 == 0 -> true
            i > 5 -> false
            else -> true
        }
        if (!shouldContinue) break
        println(i)
    }
}
```
