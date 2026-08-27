# Tradutor_infixa-posfixa
Com base no livro, Compiladores: princípios, técnicas e ferramentas¹, é um modelo de tradutor de expressões infixa para pósfixa; feito em três arquivos, analex.c, sint.c; analex.h; e seu processamento em distribuição Linux.

# Sobre a lógica aplicada
A priori é necessário o entendimento sobre os conceitos de oprações infixa e posfixa.

Para o entendimento humano sobre expressões arritiméticas, é utilizado a notação Infixada, apresentada como um operador entre os operandos, siga o modelo abaixo:
a) 2 + 3; 
b) 2 + 3 * ( 6 - 4 );

Entretanto, no computador utiliza-se a notação Pós-Fixada, aprsenentada com todos opreandos ao lado esquerdo e os operadores ao lado direito; e execução é feita a cada dois operando localizados à direita, é apilacado o operador à esquerda, tornando necessário apenas a utilizção de operadores como +, -; *, /, e mesmo assim seguindo a ordem de precedência métematica, siga o modelo abaixo, que faz equivalência ao modelo anterior:
a) 2 3 +;
b) 2 3 6 4 - * +;
b.1) 2 3 2 * + (Foi consumido, 6 - 4);
b.2) 2 6 + (Foi consumido, 3 * 2);
b.3) 8 (Foi consumido, 2 + 6);

Logo, o programa faz essa tradução de modo automático.
a) Entrada do usuário:
`` 2 + 3; ``
Saída do sitema:
`` 2 3 + ``

b) Entrada do usuário:
`` 2 + 3 * ( 6 - 4 ); ``
Saída do sitema:
`` 2 3 6 4 - * + ``

# Para utilização
1. Manter todos os arquivos, analex.c, sint.c; analex.h, agrupados em uma pasta única.
2. Execução por prompt de comando, seguir modelo abaixo:
2.1 ```seuDireótio\Tradutor_infixa-posfixa\>gcc -o "NomeExecutável" analex.c analex.h sint.c```
2.2 ```seuDireótio\Tradutor_infixa-posfixa\>"NomeExecutável"```
2.3 ```seuDireótio\Tradutor_infixa-posfixa\>"Expressão"²;```
3. A Expressão², precisa seguir essa estrutura:
3.1 (N³ O⁴ N³)⁺;
3.2 Sendo que N³ -> [0-9]; O⁴ -> + | - | * | / |; 

AHO, A. V.;LAM, M. S.; SETHI, R.; ULLMAN, J. D. Compiladores: princípios, técnicas e ferramentas. 2. ed. São Paulo: Pearson Addison-Wesley, 2008.¹
Expressão², é a expressão arritimética dada pelo usuário.²
