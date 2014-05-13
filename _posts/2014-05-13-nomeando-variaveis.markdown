---
layout: post
title:  "Nomeando Variáveis"
date:   2014-05-13 10:10:00
categories: programming portuguese
---


O que é um bom nome de variável? Neste texto *destinado aos iniciantes em programação*, vamos tentar responder essa pergunta.

Suponha que alguém tenha escrevido, em C, o seguinte programa para calcular o IMC (Índice de Massa Corporal). Tente entendê-lo.

```c
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


Analise agora o mesmo programa, com outros nomes de variável.

```c
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

No primeiro programa, nomes como `a` e `x` não dão qualquer pista do que as variáveis representam. Já no segundo, os nomes são bem mais claros, o que facilita  a compreensão do código, principalmente da parte que contém a fórmula.

Suponhamos agora que alguém implemente o programa abaixo, para calcular a massa média de um conjunto de pessoas.

```c
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

```c
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

Nesse caso, os nomes longos que ocorrem na primeira versão deixaram o código denso, difícil de ser compreendido. Os nomes usados na segunda versão são concisos e suficientemente claros. Inclusive, não há razão para que se use `indice_vetor` em vez de simplesmente `i`, que é um nome padrão para índices de vetores.

Neste ponto -- evitando estender o texto além do necessário -- podemos dizer que um bom nome de variável tem significado claro no contexto em que é usado. Quando se observa a expressão `massas[i]`, fica claro que apesar de ser uma única letra `i` representa os índices do vetor `massas`. O mesmo pode ser dito sobre a variável `total`, que isolada teria pouco significado, mas no contexto em que ocorre, claramente representa o total das massas.

Para finalizar, veja o exemplo abaixo. O uso do nome `c` prejudica a compreensão do código? Teria sido melhor usar `caracter_alfabetico`?

```c
int main(void) {
	char c;

	c = 'a';
	do {
		printf("%c\n", c);
		c++;
	} while (c != 'z');

	return 0;
}
```

