# Loops Aninhados em C: Exemplos Detalhados

Os loops aninhados são estruturas de repetição colocadas uma dentro da outra, permitindo executar operações mais complexas. Vamos explorar 5 exemplos detalhados em C usando FOR, WHILE e DO WHILE.

## Exemplo 1: Padrão de Asteriscos com Loop FOR Aninhado

**Código em C:**
```c
#include <stdio.h>

int main() {
    int i, j;
    
    // Imprime um triângulo retângulo de asteriscos
    for (i = 1; i <= 5; i++) {
        for (j = 1; j <= i; j++) {
            printf("* ");
        }
        printf("\n");
    }
    
    return 0;
}
```

**Explicação Passo a Passo:**

1. O loop externo (variável `i`) controla o número de linhas (de 1 a 5)
2. Para cada linha, o loop interno (variável `j`) executa de 1 até o valor de `i`
3. Em cada iteração do loop interno, imprimimos um asterisco seguido de espaço
4. Após o loop interno terminar, imprimimos uma quebra de linha com `printf("\n")`
5. O processo continua até que todas as 5 linhas sejam impressas

**Saída:**
```
* 
* * 
* * * 
* * * * 
* * * * * 
```

## Exemplo 2: Tabuada com Loop FOR Aninhado

**Código em C:**
```c
#include <stdio.h>

int main() {
    int numero, multiplicador, resultado;
    
    // Gera a tabuada do 1 ao 5
    for (numero = 1; numero <= 5; numero++) {
        printf("\nTabuada do %d:\n", numero);
        
        for (multiplicador = 1; multiplicador <= 10; multiplicador++) {
            resultado = numero * multiplicador;
            printf("%d x %d = %d\n", numero, multiplicador, resultado);
        }
    }
    
    return 0;
}
```

**Explicação Passo a Passo:**

1. O loop externo itera de 1 a 5, representando cada número da tabuada
2. Para cada número, imprimimos um cabeçalho indicando a tabuada atual
3. O loop interno itera de 1 a 10, representando os multiplicadores
4. Dentro do loop interno, calculamos o produto do número pelo multiplicador
5. Imprimimos a operação completa com o resultado usando `printf`

## Exemplo 3: Matriz com Loop WHILE Aninhado

**Código em C:**
```c
#include <stdio.h>

int main() {
    int linhas = 3, colunas = 4;
    int i = 0, j = 0;
    
    // Imprime uma matriz de números usando WHILE
    while (i < linhas) {
        j = 0;  // Reinicia j para cada nova linha
        
        while (j < colunas) {
            printf("%d,%d\t", i, j);
            j++;
        }
        
        printf("\n");
        i++;
    }
    
    return 0;
}
```

**Explicação Passo a Passo:**

1. Inicializamos `i` e `j` com 0, que serão nossos contadores
2. O loop externo WHILE controla as linhas, executando enquanto `i < linhas`
3. Para cada linha, reiniciamos `j = 0` para começar da primeira coluna
4. O loop interno WHILE controla as colunas, executando enquanto `j < colunas`
5. Imprimimos a posição atual (i,j) seguido de uma tabulação (`\t`)
6. Incrementamos `j` após cada impressão no loop interno
7. Após completar uma linha, imprimimos uma quebra de linha e incrementamos `i`

**Saída:**
```
0,0     0,1     0,2     0,3
1,0     1,1     1,2     1,3
2,0     2,1     2,2     2,3
```

## Exemplo 4: Combinação de FOR e DO WHILE

**Código em C:**
```c
#include <stdio.h>

int main() {
    int i, j;
    
    // Loop externo FOR e loop interno DO WHILE
    for (i = 1; i <= 3; i++) {
        printf("Grupo %d: ", i);
        
        j = 1;
        do {
            printf("%d ", i * j);
            j++;
        } while (j <= 4);
        
        printf("\n");
    }
    
    return 0;
}
```

**Explicação Passo a Passo:**

1. O loop externo FOR itera de 1 a 3
2. Para cada iteração do loop externo, imprimimos um cabeçalho "Grupo X: "
3. Inicializamos `j = 1` antes de entrar no loop interno
4. O loop interno DO WHILE executa pelo menos uma vez, mesmo que a condição seja falsa
5. Dentro do loop interno, calculamos e imprimimos o produto de `i` e `j`
6. Incrementamos `j` após cada impressão
7. Verificamos a condição `j <= 4` para continuar ou sair do loop interno
8. Após o loop interno terminar, imprimimos uma quebra de linha

**Saída:**
```
Grupo 1: 1 2 3 4 
Grupo 2: 2 4 6 8 
Grupo 3: 3 6 9 12 
```

## Exemplo 5: Dois Loops DO WHILE Aninhados

**Código em C:**
```c
#include <stdio.h>

int main() {
    int i = 0, j;
    
    // Ambos os loops são DO WHILE
    do {
        j = 0;
        
        printf("Linha %d: ", i);
        
        do {
            // Imprime números em ordem alternada (par/ímpar)
            if ((i + j) % 2 == 0) {
                printf("P ");  // Posição com soma par
            } else {
                printf("I ");  // Posição com soma ímpar
            }
            
            j++;
        } while (j < 5);
        
        printf("\n");
        i++;
    } while (i < 4);
    
    return 0;
}
```

**Explicação Passo a Passo:**

1. Inicializamos `i = 0` antes do loop externo
2. O loop externo DO WHILE começa e executa seu bloco de código
3. Para cada iteração do loop externo, reiniciamos `j = 0`
4. Imprimimos um cabeçalho para cada linha
5. O loop interno DO WHILE executa 5 vezes (enquanto `j < 5`)
6. Dentro do loop interno, verificamos se a soma de `i + j` é par ou ímpar
7. Imprimimos "P" se for par ou "I" se for ímpar
8. Incrementamos `j` após cada verificação
9. Após o loop interno terminar, imprimimos uma quebra de linha e incrementamos `i`
10. O loop externo verifica se `i < 4` para continuar ou terminar

**Saída:**
```
Linha 0: P I P I P 
Linha 1: I P I P I 
Linha 2: P I P I P 
Linha 3: I P I P I 
```
