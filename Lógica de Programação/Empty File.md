xplicação: Imprime uma tabela de multiplicação 5x5. O loop externo controla as linhas (i) e o interno as colunas (j). Total de 25 iterações (5 × 5).
Exemplo 2: Triângulo Numérico
c
#include <stdio.h>
int main() {
    for(int i = 1; i <= 5; i++) {
        for(int j = 1; j <= i; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }
    return 0;
}

Explicação: Gera um triângulo com números crescentes por linha (1; 1 2; 1 2 3; etc.). O loop interno depende de i para limitar as colunas.
Exemplo 3: Matriz 3x3
c
#include <stdio.h>
int main() {
    int matriz[3][3] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    for(int i = 0; i < 3; i++) {
        for(int j = 0; j < 3; j++) {
            printf("%d ", matriz[i][j]);
        }
        printf("\n");
    }
    return 0;
}

Explicação: Exibe uma matriz 3x3. O loop externo itera pelas linhas e o interno pelas colunas, acessando cada elemento.
Exemplo 4: Padrão de Asteriscos
c
#include <stdio.h>
int main() {
    for(int i = 5; i >= 1; i--) {
        for(int j = 1; j <= i; j++) {
            printf("* ");
        }
        printf("\n");
    }
    return 0;
}

Explicação: Cria um triângulo decrescente de asteriscos (5, 4, 3, 2, 1). O loop externo diminui i, e o interno imprime * conforme o valor de i.
Exemplo 5: Contagem Combinada
c
#include <stdio.h>
int main() {
    for(int i = 0; i < 4; i++) {
        for(int j = 0; j < 3; j++) {
            printf("Par (%d, %d)\n", i, j);
        }
    }
    return 0;
}

Explicação: Gera todas as combinações de i (0 a 3) e j (0 a 2), totalizando 12 pares (4 × 3). Útil para percorrer coordenadas ou índices.
5 Exemplos de Loops WHILE Aninhados
Exemplo 1: Contagem Simples
c
#include <stdio.h>
int main() {
    int x = 0;
    while(x < 3) {
        int y = 0;
        while(y < 2) {
            printf("x=%d, y=%d\n", x, y);
            y++;
        }
        x++;
    }
    return 0;
}

Explicação: Imprime pares de x (0 a 2) e y (0 a 1). Total de 6 iterações (3 × 2). Cada loop interno reinicia y.
Exemplo 2: Divisores
c
#include <stdio.h>
int main() {
    int num = 1;
    while(num <= 5) {
        int div = 1;
        while(div <= num) {
            if(num % div == 0) printf("%d ", div);
            div++;
        }
        printf("são divisores de %d\n", num);
        num++;
    }
    return 0;
}

Explicação: Lista os divisores de 1 a 5. O loop externo testa cada número, e o interno verifica divisores até o número atual.
Exemplo 3: Contagem Decrescente
c
#include <stdio.h>
int main() {
    int a = 3;
    while(a > 0) {
        int b = a;
        while(b > 0) {
            printf("%d ", b);
            b--;
        }
        printf("\n");
        a--;
    }
    return 0;
}

Explicação: Gera um padrão decrescente (3 2 1; 2 1; 1). O loop interno começa de a e diminui até 0.
Exemplo 4: Verificação de Pares
c
#include <stdio.h>
int main() {
    int i = 0;
    while(i < 4) {
        int j = 0;
        while(j < 3) {
            if((i + j) % 2 == 0) printf("(%d, %d) é par\n", i, j);
            j++;
        }
        i++;
    }
    return 0;
}

Explicação: Verifica se a soma de i e j é par em 12 combinações (4 × 3). Apenas pares com soma par são impressos.
Exemplo 5: Progressão Geométrica
c
#include <stdio.h>
int main() {
    int base = 1;
    while(base <= 4) {
        int exp = 0;
        while(exp < 3) {
            int res = 1;
            for(int k = 0; k < exp; k++) res *= base; // Auxiliar para potência
            printf("%d^%d = %d\n", base, exp, res);
            exp++;
        }
        base++;
    }
    return 0;
}

Explicação: Calcula potências de 1 a 4 com expoentes 0 a 2. O loop externo muda a base, o interno o expoente (12 resultados).
5 Exemplos de Loops DO WHILE Aninhados
Exemplo 1: Contagem Básica
c
#include <stdio.h>
int main() {
    int i = 0;
    do {
        int j = 0;
        do {
            printf("i=%d, j=%d\n", i, j);
            j++;
        } while(j < 2);
        i++;
    } while(i < 3);
    return 0;
}

Explicação: Similar ao WHILE, mas executa pelo menos uma vez. Gera 6 pares (3 × 2) de i (0 a 2) e j (0 a 1).
Exemplo 2: Padrão Crescente
c
#include <stdio.h>
int main() {
    int linha = 1;
    do {
        int estrelas = 0;
        do {
            printf("* ");
            estrelas++;
        } while(estrelas < linha);
        printf("\n");
        linha++;
    } while(linha <= 4);
    return 0;
}

Explicação: Cria um triângulo de asteriscos (1, 2, 3, 4). O loop interno imprime estrelas conforme o número da linha.
Exemplo 3: Tabuada Parcial
c
#include <stdio.h>
int main() {
    int num = 2;
    do {
        int mult = 1;
        do {
            printf("%d x %d = %d\n", num, mult, num * mult);
            mult++;
        } while(mult <= 3);
        num++;
    } while(num <= 4);
    return 0;
}

Explicação: Imprime tabuadas de 2 a 4, até o multiplicador 3. Total de 9 linhas (3 números × 3 multiplicadores).
Exemplo 4: Contagem Regressiva
c
#include <stdio.h>
int main() {
    int x = 3;
    do {
        int y = 2;
        do {
            printf("x=%d, y=%d\n", x, y);
            y--;
        } while(y >= 0);
        x--;
    } while(x > 0);
    return 0;
}

Explicação: Gera pares decrescentes de x (3 a 1) e y (2 a 0). Total de 9 iterações (3 × 3).
Exemplo 5: Verificação de Múltiplos
c
#include <stdio.h>
int main() {
    int a = 1;
    do {
        int b = 1;
        do {
            if(a * b % 3 == 0) printf("%d x %d = %d (múltiplo de 3)\n", a, b, a*b);
            b++;
        } while(b <= 5);
        a++;
    } while(a <= 3);
    return 0;
}

Explicação: Identifica múltiplos de 3 em produtos de a (1 a 3) e b (1 a 5). Total de 15 iterações, mas só imprime quando a condição é verdadeira.
