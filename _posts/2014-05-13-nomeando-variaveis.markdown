---
layout: post
title:  "Nomeando Variáveis"
date:   2014-05-13 10:10:00
categories: programming portuguese
---


O que se considera um bom nome de variável? Este texto, *destinado a iniciantes em programação*, foi escrito para apontar alguns critérios que possam levar à resposta para essa pergunta.

Suponha que alguém tenha escrevido o seguinte programa, na Linguagem C, para calcular o IMC (Índice de Massa Corporal) de um indivíduo. Analisando o código, tente responder:

- Quais dados de entrada são necessários para o cálculo?
- Como se determina o valor do IMC?

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


Analise agora o mesmo programa, com outros nomes de variável, e tente novamente responder as perguntas.

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

No primeiro programa, nomes como `a` e `x` não dão qualquer pista do que as variáveis representam. Já no segundo, os nomes são bem mais claros, o que facilita  a compreensão do código, principalmente da parte que contém a fórmula.

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

Nesse exemplo, os nomes longos que ocorrem na primeira versão deixaram o código denso, difícil de ser compreendido. Os nomes usados na segunda versão são concisos e suficientemente claros. Inclusive, não há razão para que se use `indice_vetor` em vez de simplesmente `i`, que é um nome padrão para índices de vetores.

Quais são as características dos nomes que foram considerados bons? Analisando os exemplos, pode-se dizer que *um bom nome de variável tem significado claro no contexto em que é usado*. Quando se observa a expressão `massas[i]` fica claro que `i`, apesar de ser uma única letra, representa os índices do vetor `massas`. O mesmo pode ser dito sobre a variável `total`, que isolada teria pouco significado, mas no contexto em que ocorre representa claramente a soma total das massas.

Para finalizar, veja o exemplo abaixo. O nome `c` tem significado claro no contexto em que é usado? Teria sido melhor usar `caracter_alfabetico`?

```c++
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

