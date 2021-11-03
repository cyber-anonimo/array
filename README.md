#include <iostream>
#include <ctime>
#include <cstdlib>

#define LINHA 5
#define COLUNA 5

// assinatura de função
int somaLinhas(int vetor[LINHA][COLUNA]);
int somaColunas(int vetor[LINHA][COLUNA]);
int somaDiagonais(int vetor[LINHA][COLUNA]);
  
  
  
  
#include "atividade.h"

int main (){
    srand(time(NULL));

    std::cout << "Atividade com Array " << LINHA << " X  " << COLUNA << "\n";

    int vetor[LINHA][COLUNA];

/*
       			//colunas
		    | 0 | 1 | 2 | 3 | 4 |
		    | 0 | 1 | 2 | 3 | 4 |
//linhas    | 0 | 1 | 2 | 3 | 4 |
		    | 0 | 1 | 2 | 3 | 4 |
		    | 0 | 1 | 2 | 3 | 4 | 
*/

			

	// o preechimento com números aleatórios no array
    for (int linha = 0; linha < LINHA; linha++) {
        for (int coluna = 0; coluna < COLUNA; coluna++) {
            vetor[linha][coluna] = rand() % 10;
            if(linha == coluna){
            	std::cout << "| " << vetor[linha][coluna] << " |";
			}else{
				std::cout << "| " << vetor[linha][coluna] << " |";
			}            
        }
        std::cout << "\n";
    }
	
	std::cout << "\n";
	std::cout << "Soma Linhas\n";
    somaLinhas(vetor);
    
    std::cout << "\n";
	std::cout << "Soma Colunas\n";
    somaColunas(vetor);

    return 0;
}

int somaLinhas(int vetor[LINHA][COLUNA]){
    // SOMA LINHAS
    int linhasSomadas[5];
    for (int linha = 0; linha < LINHA; linha++){
        for (int coluna = 0; coluna < COLUNA; coluna++){
		    std::cout << "| " << vetor[linha][coluna] << " |";        	
            linhasSomadas[linha] += vetor[linha][coluna];
        }
        std::cout << " = " << linhasSomadas[linha] << "\n";
    }
    return 0;
}

int somaColunas(int vetor[LINHA][COLUNA]){
    // SOMA COLUNAS
    int diagonaisSomadas[5];
    for (int linha = 0; linha < LINHA; linha++){
    	for (int coluna = 0; coluna < COLUNA; coluna++){
    			std::cout << "| " << vetor[linha][coluna] << " |";  
	    		if(linha == coluna){
	    			diagonaisSomadas[coluna] += vetor[linha][coluna];
				}
		}
		std::cout << "\n";		
	}
	std::cout << "============================\n";		
	for (int i = 0; i < 5; i++) {
		std::cout << "| " << diagonaisSomadas[i] << " |"; 
	}
    return 0;
}
