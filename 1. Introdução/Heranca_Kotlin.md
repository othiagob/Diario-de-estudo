
# Herança em Kotlin

## Exemplo 1: Cachorro (Dog)

```kotlin
open class Dog {                
    open fun sayHello() {       
        println("wow wow!")
    }
}

class Yorkshire : Dog() {       
    override fun sayHello() {   
        println("wif wif!")
    }
}

fun main() {
    val dog: Dog = Yorkshire()
    dog.sayHello()
}
```

### Explicação
1. `open class Dog`  
   - A palavra-chave `open` permite que a classe seja herdada por outras classes.
   
2. `open fun sayHello()`  
   - Método marcado como `open`, permitindo sobrescrita em subclasses.

3. `class Yorkshire : Dog()`  
   - Subclasse que herda da classe `Dog`.

4. `override fun sayHello()`  
   - Sobrescreve o comportamento do método `sayHello`.

5. **Polimorfismo no `main`**  
   - A instância de `Yorkshire` usa o método sobrescrito mesmo que seja referenciada como tipo `Dog`.

---

### Exemplo extra 1: Gato (Cat)

```kotlin
open class Animal {
    open fun makeSound() {
        println("Some generic animal sound")
    }
}

class Cat : Animal() {
    override fun makeSound() {
        println("meow meow!")
    }
}

fun main() {
    val animal: Animal = Cat()
    animal.makeSound()  // Saída: meow meow!
}
```

---

## Exemplo 2: Tigre (Tiger)

```kotlin
open class Tiger(val origin: String) {
    fun sayHello() {
        println("A tiger from $origin says: grrhhh!")
    }
}

class SiberianTiger : Tiger("Siberia")

fun main() {
    val tiger: Tiger = SiberianTiger()
    tiger.sayHello()
}
```

### Explicação
1. `open class Tiger(val origin: String)`  
   - Classe base com um parâmetro de construtor.

2. `class SiberianTiger : Tiger("Siberia")`  
   - Subclasse que define o valor de `origin` no construtor.

3. **Comportamento do `main`**  
   - O método `sayHello` é herdado e chamado diretamente.

---

### Exemplo extra 1: Pássaro (Bird)

```kotlin
open class Bird(val color: String) {
    fun describe() {
        println("A bird with $color feathers")
    }
}

class Parrot : Bird("green")

fun main() {
    val bird: Bird = Parrot()
    bird.describe()  // Saída: A bird with green feathers
}
```

---

## Exemplo 3: Leão (Lion)

```kotlin
open class Lion(val name: String, val origin: String) {
    fun sayHello() {
        println("$name, the lion from $origin says: graoh!")
    }
}

class Asiatic(name: String) : Lion(name = name, origin = "India")

fun main() {
    val lion: Lion = Asiatic("Rufo")
    lion.sayHello()
}
```

### Explicação
1. `open class Lion(val name: String, val origin: String)`  
   - Classe base com parâmetros para nome e origem.

2. `class Asiatic(name: String)`  
   - Subclasse fixa o valor de `origin` como "India".

3. **Comportamento no `main`**  
   - Instância personalizada com nome "Rufo".

---

### Exemplo extra 1: Peixe (Fish)

```kotlin
open class Fish(val name: String, val habitat: String) {
    fun introduce() {
        println("$name lives in $habitat")
    }
}

class Clownfish(name: String) : Fish(name, habitat = "coral reefs")

fun main() {
    val fish: Fish = Clownfish("Nemo")
    fish.introduce()  // Saída: Nemo lives in coral reefs
}
```
