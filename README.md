#include <stdio.h>
#include <stdlib.h>

//Daniel Dourado Pereira dos Santos0 Sistemas de Informção 4° Periodo

struct noArvovre{
  char Raiz;
  struct noArvovre* esq;
  struct noArvovre* dir;
};

typedef struct noArvovre no;

no* criar_no(char Raiz,no* esq, no* dir){
	no* n = malloc(sizeof(no ));
	n -> Raiz = Raiz;
	n -> esq = esq;
	n -> dir = dir;
return n;
}

void emordem(no* n){
	if (n !=NULL){
	emordem(n -> esq);
	printf("%c", n -> Raiz );
    emordem(n -> dir);
    }
}

void posordem(no* n){
	if (n !=NULL){
	
	posordem(n -> esq);
	posordem(n -> dir);
	printf("%c", n -> Raiz );
    }
}

void preordem(no* n){
	if (n !=NULL){
	printf("%c", n -> Raiz );
	preordem(n -> esq);
	preordem(n -> dir);
    }
}
void imprimirArv(no* n){
	if (n !=NULL){
	printf("%c", n -> Raiz );
	imprimirArv(n -> esq);
	imprimirArv(n -> dir);
    }
}
void main(){
	no* nono = criar_no('A',criar_no(('B'),NULL,NULL), criar_no(('C'),NULL,NULL));
//	imprimirArv(nono);
    printf("\n Em Ordem: ");
	emordem(nono);
	printf("\n Pos Ordem: ");
	posordem(nono);
	printf("\n Pre Ordem: ");
	preordem(nono);
}
