---
layout: post
title:  "Nomeando Variáveis"
date:   2014-05-13 10:10:00
categories: programming portuguese
---


*Este texto é destinado a iniciantes em programação.*

Vamos tentar responder a pergunta: o que é um bom nome de variável?

Suponha que alguém tenha escrevido o seguinte programa para calcular o IMC de um indivíduo. Analisando o código, tente responder:

1. Quais dados de entrada são necessários para o cálculo?
1. Como se determina o valor do IMC?

```c++
int main(void) {
	float a, b, x;

	printf("altura: ");
	scanf("%f", &a);
	printf("massa: ");
	scanf("%f", &b);

	x = b / (a * a);
	printf("IMC: %.2f", x);

	return 0;
}
```


Analise agora o mesmo programa, com outros nomes de variável, e tente novamente responder:

1. Quais dados de entrada são necessários para o cálculo?
1. Como se determina o valor do IMC?


```c++
int main(void) {
	float altura, massa, imc;

	printf("altura: ");
	scanf("%f", &altura);
	printf("massa: ");
	scanf("%f", &massa);

	imc = massa / (altura * altura);
	printf("IMC: %.2f", imc);

	return 0;
}
```


Qual das duas versões é mais fácil de se entender?

No primeiro programa, nomes como `a` e `x` não dão qualquer pista do que as variáveis representam. Já no segundo, os nomes são bem mais claros, facilitando a compreensão do código, principalmente da parte que contém a fórmula do IMC.

Suponhamos agora que alguém implemente o programa abaixo, para calcular a massa média de um conjunto de pessoas.

```c++
int main(void) {
	double massas_das_pessoas[5] = {84.5, 102.0, 67.3, 59.1, 97.8};
	int indice_vetor;
	double massa_total, massa_media;

	massa_total = 0;
	for (indice_vetor=0; indice_vetor < 5; indice_vetor++) {
		massa_total += massas_das_pessoas[indice_vetor];
	}

	massa_media = massa_total / 5;
	printf("Massa média: %.2f", massa_media);

	return 0;
}
```

Compare-o com essa outra versão.

```c++
int main(void) {
	double massas[5] = {84.5, 102.0, 67.3, 59.1, 97.8};
	int i;
	double total, media;

	total = 0;
	for (i=0; i < 5; i++) {
		total += massas[i];
	}

	media = total / 5;
	printf("Massa média: %.2f", media);

	return 0;
}
```

Qual das duas versões é mais fácil de se entender?

Nesse caso, os nomes longos -- como `massas_das_pessoas` -- deixaram o código da primeira versão do programa denso, difícil de ser lido. Os nomes usados na segunda versão são concisos e suficientemente claros. Inclusive, não há razão para que se use `indice_vetor` em vez de simplesmente `i`, que é um nome padrão para índices de vetores, assim como `j` e `k`.

Quais são, então, as características dos bons nomes de variáveis? Analisando os exemplos, pode-se dizer que *um bom nome de variável tem significado claro no contexto em que é usado*.

No último exemplo, fica claro que na expressão `massas[i]` a variável `i`, apesar de ser uma única letra, representa os índices do vetor `massas`. O mesmo vale para a variável `total`, que isolada não teria muito significado, mas quando é considerada no contexto representa claramente a soma total das massas.

Para finalizar, veja o exemplo abaixo. O nome `c` tem significado claro no contexto em que é usado? Teria sido melhor chamar a variável de `caracter_alfabetico`?

```c++
int main(void) {
	char c;

	c = 'a';
	do {
		printf("%c\n", c);
		c++;
	} while (c <= 'z');

	return 0;
}
```
