

## O que é lógica de programação?

Lógica de programação é a habilidade de estruturar um conjunto de instruções para resolver um problema utilizando um computador. Pense nisso como seguir uma receita de bolo: você precisa organizar os ingredientes e seguir os passos corretamente para obter um resultado esperado.

Exemplo no mundo real: Se você precisa atravessar uma rua movimentada, você segue um conjunto de regras lógicas:

1. Olha para os dois lados.
2. Espera o semáforo ficar verde.
3. Atravesse apenas quando for seguro.

Da mesma forma, um programa segue uma sequência de instruções para atingir um objetivo.

*Exemplo de código simples em C:*

```c
#include <stdio.h>

int main() {
    printf("Ola, mundo!\n");
    return 0;
}
```

*Esse pequeno programa imprime "Ola, mundo!" na tela. O computador segue exatamente os comandos especificados na ordem correta.*

---

## *Algoritmos*

### *O que é um algoritmo?*

*Um algoritmo é um conjunto de passos finitos e bem definidos para resolver um problema.*

### *Características de um bom algoritmo:*

1. ***Finitude***: Deve terminar em algum momento.
2. ***Precisão***: Cada passo deve ser claro e sem ambiguidades.
3. ***Clareza***: Deve ser compreensível e estruturado.

### *Representação de algoritmos:*

- ***Pseudocódigo***: Uma representação textual semelhante a uma linguagem de programação.
- ***Fluxogramas***: Representa graficamente um algoritmo.

*Exemplo de pseudocódigo para somar dois números:*

```
Inicio
   Leia A
   Leia B
   Soma <- A + B
   Escreva Soma
Fim
```

*Em C:*

```c
#include <stdio.h>

int main() {
    int a, b, soma;
    printf("Digite dois numeros: ");
    scanf("%d %d", &a, &b);
    soma = a + b;
    printf("A soma eh: %d\n", soma);
    return 0;
}
```

---

## *Pensamento Computacional*

*Pensamento computacional é a capacidade de resolver problemas de forma estruturada. Ele é composto por quatro princípios:*

### *1. Decomposição*

*Dividir um problema grande em partes menores e mais gerenciáveis.*

***Exemplo:*** Para calcular a média de notas de uma turma, podemos dividir assim:

1. *Coletar as notas.*
2. *Somar todas as notas.*
3. *Dividir pelo número total de alunos.*

### *2. Abstração*

*Ignorar detalhes irrelevantes e focar no essencial.*

***Exemplo:*** Ao dirigir um carro, você se preocupa com o volante e pedais, não com o funcionamento interno do motor.

### *3. Reconhecimento de padrões*

*Identificar similaridades em problemas para criar soluções mais eficientes.*

***Exemplo:*** Códigos que calculam média são semelhantes, independentemente se aplicados a notas de alunos ou vendas mensais.

### *4. Algoritmos*

*Criar sequências lógicas para resolver problemas.*

***Exemplo:*** Para determinar se um número é par ou ímpar em C:

```c
#include <stdio.h>

int main() {
    int numero;
    printf("Digite um numero: ");
    scanf("%d", &numero);
    
    if (numero % 2 == 0) {
        printf("O numero eh par.\n");
    } else {
        printf("O numero eh impar.\n");
    }
    return 0;
}
```

---

## *Sequência Lógica*

*A ordem das instruções em um programa é essencial para seu funcionamento correto. Se você mudar a ordem dos passos em uma receita de bolo, pode acabar com um desastre culinário!*

*Em programação, uma sequência lógica segue três estruturas básicas:*

### *1. Sequencial*

*Os comandos são executados um após o outro.*

```c
#include <stdio.h>

int main() {
    printf("Passo 1\n");
    printf("Passo 2\n");
    printf("Passo 3\n");
    return 0;
}
```

*Saída esperada:*

```
Passo 1
Passo 2
Passo 3
```

### *2. Condicional (Decisão)*

*O fluxo do programa pode mudar dependendo de uma condição.*

```c
int idade;
printf("Digite sua idade: ");
scanf("%d", &idade);
if (idade >= 18) {
    printf("Voce e maior de idade.\n");
} else {
    printf("Voce e menor de idade.\n");
}
```

### *3. Repetição (Laços)*

*Executa um bloco de código várias vezes.*

```c
#include <stdio.h>

int main() {
    int i;
    for (i = 1; i <= 5; i++) {
        printf("Iteracao %d\n", i);
    }
    return 0;
}
```

*Saída:*

```
Iteracao 1
Iteracao 2
Iteracao 3
Iteracao 4
Iteracao 5
```

---

## *Conclusão*

*Compreender a lógica de programação é essencial para escrever código eficiente e resolver problemas. A prática constante, junto com a compreensão dos conceitos de algoritmos, pensamento computacional e sequência lógica, ajudará a desenvolver melhores soluções e aprimorar suas habilidades em C!*
