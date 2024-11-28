# Classes em Kotlin: Guia Completo

## Código Original
```kotlin
class Customer                                  // 1
class Contact(val id: Int, var email: String)   // 2
fun main() {
    val customer = Customer()                   // 3
    
    val contact = Contact(1, "mary@gmail.com")  // 4
    println(contact.id)                         // 5
    contact.email = "jane@gmail.com"            // 6
}
```

## Análise Detalhada

### Definição das Classes

#### 1. Classe Simples: `class Customer`
- Esta é a definição de classe mais simples possível em Kotlin
- Um "molde" genérico sem propriedades ou construtor personalizado
- **Metáfora**: Como um formulário em branco, pronto para ser preenchido

#### 2. Classe com Propriedades: `class Contact(val id: Int, var email: String)`
- Definição de classe com propriedades no construtor primário
- `val id: Int`:
  * Propriedade somente-leitura (imutável)
  * Não pode ser alterada após a criação do objeto
  * **Analogia**: Como um documento de identidade fixo

- `var email: String`:
  * Propriedade mutável
  * Pode ser modificada posteriormente
  * **Analogia**: Como um endereço de contato atualizável

### Função Principal: Detalhes

#### 3. Criação de Instância Simples: `val customer = Customer()`
- Cria um objeto da classe `Customer`
- Sem parâmetros ou configurações especiais
- **Metáfora**: Como tirar um formulário em branco do arquivo

#### 4. Criação de Contato: `val contact = Contact(1, "mary@gmail.com")`
- Instância da classe `Contact`
- Fornece ID e email inicial
- **Analogia**: Preenchendo um formulário de contato com dados iniciais

#### 5. Acessando Propriedade: `println(contact.id)`
- Imprime o ID do contato
- Acesso a propriedade somente-leitura
- **Exemplo**: Como ler o número de identificação de um documento

#### 6. Modificando Propriedade: `contact.email = "jane@gmail.com"`
- Altera o email do contato
- Possível por ser uma propriedade `var`
- **Metáfora**: Atualizando um endereço de contato

## Exemplos Adicionais

### Exemplo 1: Sistema de Biblioteca
```kotlin
class Book(val isbn: String, var title: String, var isAvailable: Boolean = true) {
    fun checkOut() {
        if (isAvailable) {
            isAvailable = false
            println("Livro emprestado com sucesso!")
        } else {
            println("Livro já está emprestado.")
        }
    }
}

fun main() {
    val book = Book("123-456", "Kotlin para Iniciantes")
    println(book.title)  // Imprime o título
    book.checkOut()      // Empresta o livro
}
```

### Exemplo 2: Sistema de Usuário
```kotlin
class User(val username: String, var age: Int, var isActive: Boolean = true) {
    fun birthday() {
        age++
        println("Feliz aniversário! Nova idade: $age")
    }
    
    fun deactivate() {
        isActive = false
        println("Usuário desativado.")
    }
}

fun main() {
    val user = User("joao_silva", 25)
    user.birthday()      // Incrementa idade
    user.deactivate()    // Desativa usuário
}
```

## Diferenças entre `val` e `var`

### `val` (Imutável)
- Valor definido no momento da criação
- Não pode ser modificado
- **Analogia**: Documento de identidade fixo

### `var` (Mutável)
- Valor pode ser alterado após a criação
- Flexível para atualizações
- **Analogia**: Endereço que pode mudar

## Pontos Principais de Aprendizado

1. Kotlin permite definir propriedades diretamente no construtor
2. `val` e `var` controlam a mutabilidade das propriedades
3. Classes podem ser simples ou complexas
4. O construtor define o estado inicial do objeto

## Dicas Práticas

- Use `val` quando o valor não deve mudar
- Use `var` quando precisar de flexibilidade
- Prefira `val` sempre que possível para código mais previsível
- Utilize construtores para configuração inicial dos objetos

## Conclusão

Classes em Kotlin são poderosas e expressivas, permitindo definições claras e concisas de tipos de dados personalizados. A distinção entre `val` e `var` oferece um controle refinado sobre a mutabilidade dos dados.
