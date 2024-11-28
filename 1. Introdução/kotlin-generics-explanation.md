# Generics em Kotlin: Guia Completo

## Código Original

```kotlin
// Classe Genérica
class MutableStack<E>(vararg items: E) {              // 1
  private val elements = items.toMutableList()
  fun push(element: E) = elements.add(element)        // 2
  fun peek(): E = elements.last()                     // 3
  fun pop(): E = elements.removeAt(elements.size - 1)
  fun isEmpty() = elements.isEmpty()
  fun size() = elements.size
  override fun toString() = "MutableStack(${elements.joinToString()})"
}

// Função Genérica
fun <E> mutableStackOf(vararg elements: E) = MutableStack(*elements)

fun main() {
  val stack = mutableStackOf(0.62, 3.14, 2.7)
  println(stack)
}
```

## Análise Detalhada

### Classe Genérica: `MutableStack<E>`

#### 1. Definição da Classe Genérica
```kotlin
class MutableStack<E>(vararg items: E)
```
- `<E>` é um parâmetro de tipo genérico (type parameter)
- `vararg items: E` permite passar um número variável de elementos do tipo `E`
- **Metáfora**: Como uma caixa flexível que pode guardar qualquer tipo de objeto

#### Componentes da Classe

##### Declaração de Elementos
```kotlin
private val elements = items.toMutableList()
```
- Converte os itens passados para uma lista mutável
- Armazena os elementos internamente
- **Analogia**: Como transformar itens avulsos em uma coleção organizada

##### Método Push
```kotlin
fun push(element: E) = elements.add(element)
```
- Adiciona um novo elemento no topo da pilha
- `element: E` garante que só pode adicionar elementos do mesmo tipo
- **Metáfora**: Como empilhar um novo livro no topo de uma pilha

##### Método Peek
```kotlin
fun peek(): E = elements.last()
```
- Retorna o último elemento sem removê-lo
- **Analogia**: Olhar o título do livro no topo da pilha sem tirá-lo

##### Método Pop
```kotlin
fun pop(): E = elements.removeAt(elements.size - 1)
```
- Remove e retorna o último elemento
- **Metáfora**: Tirar o livro do topo da pilha

##### Outros Métodos Úteis
- `isEmpty()`: Verifica se a pilha está vazia
- `size()`: Retorna o número de elementos
- `toString()`: Representação em string da pilha

### Função Genérica
```kotlin
fun <E> mutableStackOf(vararg elements: E) = MutableStack(*elements)
```
- Cria uma `MutableStack` com elementos passados
- `<E>` indica que a função é genérica
- `*elements` é o operador de espalhamento (spread operator)
- **Analogia**: Como um "construtor facilitado" para criar pilhas

## Exemplos Adicionais

### Exemplo 1: Pilha de Strings
```kotlin
fun main() {
    val wordStack = mutableStackOf("Kotlin", "Java", "Python")
    println("Pilha inicial: $wordStack")
    
    wordStack.push("Rust")
    println("Após push: $wordStack")
    
    val topWord = wordStack.pop()
    println("Elemento removido: $topWord")
    println("Pilha atual: $wordStack")
}
```

### Exemplo 2: Pilha de Tipos Diferentes
```kotlin
fun main() {
    // Pilha de números
    val numberStack = MutableStack(1, 2, 3)
    
    // Pilha de objetos personalizados
    data class Person(val name: String)
    val personStack = MutableStack(
        Person("Alice"), 
        Person("Bob")
    )
    
    println("Pilha de Números: $numberStack")
    println("Pilha de Pessoas: $personStack")
}
```

## Benefícios dos Generics

1. **Flexibilidade de Tipos**
   - Permite criar estruturas de dados reutilizáveis
   - Garante segurança de tipos em tempo de compilação

2. **Reutilização de Código**
   - Evita duplicação de implementações para diferentes tipos
   - Reduz a complexidade do código

3. **Type Safety**
   - Compilador verifica os tipos em tempo de compilação
   - Previne erros de tipo em tempo de execução

## Conceitos Importantes

- `E` é uma convenção para "Element" (elemento)
- Pode usar qualquer letra ou nome como parâmetro de tipo
- Generics funcionam em classes, interfaces e funções

## Boas Práticas

- Use generics para criar estruturas de dados flexíveis
- Escolha nomes significativos para parâmetros de tipo
- Utilize quando precisar de tipos intercambiáveis
- Prefira generics a usar `Any` quando possível

## Conclusão

Generics em Kotlin oferecem uma maneira poderosa e flexível de criar código reutilizável, garantindo segurança de tipos e expressividade. A capacidade de criar classes e funções genéricas permite abstrações mais robustas e limpas.

## Desafios para Prática

1. Implemente uma fila genérica
2. Crie uma função genérica de ordenação
3. Desenvolva uma classe de cache genérica

Boa programação! 🚀👩‍💻👨‍💻
