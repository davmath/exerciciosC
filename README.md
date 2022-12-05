# exerciciosC

//[VETOR] Média entre cinco números------------------------------------------------------------------------------
int main(int argc, char *argv[]) {
	
	int v[5] = {10, 20, 30, 40, 50};
	int i;

	
	float soma;
	for(i=0;i<5;i++){
		soma += v[i];	
	}
	printf("%f", soma/5);	
}

//[MATRIZ] Percorrendo matriz-------------------------------------------------------------------------------------
int main(int argc, char *argv[]) {
	
	int mat[3][3] = {{1, 2, 3},
			 {4, 5, 6},
			 {7, 8, 9}};
	
	int i, j;
	
	printf("Imprimir primeira linha: \n");
	
	for(j=0;j<3;j++){
		printf("%d ", mat[0][j]);
	}
	
	printf("\nImprimir matriz: \n");
	
	for(i=0;i<3;i++){
		for(j=0;j<3;j++){
			printf("%d ", mat[i][j]);
		}
		printf("\n");//pula linha da matriz
	}
}

//[FUNÇÃO] Função para ler o maior número---------------------------------------------------------------------------
float maior (float num1, float num2){
	
	if(num1 > num2){
		return num1;
	}else
		return num2;	
}

int main(int argc, char *argv[]) {
	
	float x, y, m;
	printf("Insira um valor:\n");
	scanf("%f", &x);
	printf("Insira mais um valor:\n");
	scanf("%f", &y);
	m= maior(x,y);
	printf("Maior: %.2f\n", m);
}

//[VETOR COM FUNÇÕES]-----------------------------------------------------------------------------------------------
void imprime1(int v[], int n){
	int i;
	for(i=0;i<n;i++){
		printf("%d ", v[i]);
	}
}

void imprime2 (int v[5]){
	int i;
	for (i=0;i<5;i++){
		printf("%d ", v[i]);
	}
}

void imprime3 (int *v, int n){
	int i;
	for(i=0;i<n;i++){
		printf("%d ", v[i]);
	}
}

int main(int argc, char *argv[]) {
	
	int vet[5] = {1,2,3,4,5};
	
	puts("Primeiro imprime: ");
	imprime1(vet, 5);
	puts("\nSegundo imprime: ");
	imprime2(vet);
	puts("\nTerceiro imprime: ");
	imprime3(vet, 5);
	
}

[STRUCTS COM VETORES]---------------------------------------------------------------------------------------------------

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdlib.h>

#define TAM 3

struct tipo_pessoa{
	int idade;
	float peso;
	char nome[50];
};

typedef struct tipo_pessoa tipo_pessoa;

int main(int argc, char *argv[]) {
	
	tipo_pessoa lista[TAM];	
	int i;
	
	for(i=0;i<TAM;i++){
		printf("Insira os dados (%d):\n", i);
		puts("Nome: ");
		scanf("%s", &lista[i].nome);
		fflush(stdin);
		
		puts("Idade: ");
		scanf("%d", &lista[i].idade);
		fflush(stdin);
		
		puts("Peso: ");
		scanf("%f", &lista[i].peso);
		fflush(stdin);
	}
	system("cls");
	
	puts("Seus dados:\n");
	for(i=0;i<TAM;i++){
		printf("-------PESSOA %d-------\n", i);
		printf("\tNome: %s\n", lista[i].nome);
		printf("\tIdade: %d\n", lista[i].idade);
		printf("\tPeso: %f\n", lista[i].peso);
	}
	printf("---------------------------------------------\n");
}
