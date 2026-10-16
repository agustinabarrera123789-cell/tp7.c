# tp7.c
////Repositorio URL:///////
#define TAM 5
#include <stdio.h>

int main(){
	int codigos[TAM];
	float precios[TAM];

	int i;
	int posMax = 0 , posMin = 0 ;
	for(i = 0; i < TAM; i++){
	printf("producto %d \n", i + 1);
	do{
		printf("Ingrese el codigo de barra(1 a 9 cifras): ");
		scanf("%d", &codigos[i]);
		if (codigos[i] <= 0 || codigos[i] > 999999999){
			printf("Error, el codigo de barra debe estar entre 1 y 999999999.\n");
		}
	} while(codigos[i] <= 0 || codigos[i] > 999999999);
	do{
		printf("Ingrese el precio: \n");
		scanf("%f", &precios[i]);
		if (precios[i] < 0){
			printf("El precio no puede ser negativo \n");
		}
	} while(precios[i] < 0);
	printf("\n");
	}
	printf("\nCodigo             Precio\n");
	for(i = 0; i < TAM; i++){
		printf("%9d  %2.f\n", codigos[i],precios[i]);
	}
	
	for(i = 1; i < TAM; i++){
		if (precios[i] > precios[posMax]){
			posMax = i;
		}
		if (precios[i] < precios[posMin]){
			posMin = i;
		}
		printf("\nMas caro: [%d] %2.f\n", codigos[posMax], precios[posMax]);
		printf("\nMas barato: [%d] %2.f\n", codigos[posMin], precios[posMin] );
	}
	return 0;
