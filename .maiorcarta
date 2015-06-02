#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <locale.h>

struct tipo_carta{
	char naipe;
	int valor, status;
};

struct tipo_carta baralho[52];
struct tipo_carta vetC[5],vetJ[5];
int contCartas;

void criarBaralho(){
	char naipes[4]={'c','o','p','e'};
	int i,j,k;
	k=0;
	for(i=0;i<4;i++){	//i controla o indice dos naipes
		for(j=2;j<=14;j++){
			baralho[k].valor=j;
			baralho[k].naipe=naipes[i];
			baralho[k].status=0;
			k++;
		}
	}
}
void mostrarBaralho(){
	 int i;
	 for(i=0;i<52;i++){
	 	if(i%13==0){
	 		printf("\n");
		 }
	 	printf("%d%c ",baralho[i].valor,baralho[i].naipe);
	 }
	 printf("\n");
	 //procedimento para embaralhar
}
void embaralhar(){
	int i, j, cont;
	struct tipo_carta aux;
	for(cont=0;cont<200;cont++){
		i=rand()%52;	//(0-51)
		j=rand()%52;
		aux=baralho[i];
		baralho[i]=baralho[j];
		baralho[j]=aux;
	}
}


//procedimento para distribuir 5 cartas aos jogadores
void distribuirCartas(){
	int i, j;
	for(i=0;i<5;i++){
		vetC[i]=baralho[contCartas];
		contCartas++;
	}
	for(i=0;i<5;i++){
		vetJ[i]=baralho[contCartas];
		contCartas++;
	}
}
main(){
	//configurção
	setlocale(LC_ALL, "");
	srand(time(NULL));
	
	//declaração d variaveis
	int i;
	
	criarBaralho();
	embaralhar();
	mostrarBaralho();
	
	distribuirCartas();
	
	//mostrar as cartas do computador
	printf("\nCartas do computador\n");
	for(i=0;i<5;i++){
		printf("%d%c ",vetC[i].valor,vetC[i].naipe);
	}
	//mostra as cartas do jogador
	printf("\nCartas do jogador\n");
	for(i=0;i<5;i++){
		printf("%d%c ",vetJ[i].valor,vetJ[i].naipe);
	}
}
