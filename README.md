#include <iostream>
#include <ctime>
#include <cstdlib>

#define LINHA 5
#define COLUNA 5

// assinatura de função
int somaLinhas(int vetor[LINHA][COLUNA]);
int somaColunas(int vetor[LINHA][COLUNA]);
int somaDiagonais(int vetor[LINHA][COLUNA]);
int somaDiagonais2(int vetor[LINHA][COLUNA]);

#include "atividade.h"
using namespace std;
int main (){
    srand(time(NULL));

    cout << "Atividade com Array " << LINHA << " X  " << COLUNA << "\n";

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
    for (int linha = 0; linha < LINHA; linha++){
        for (int coluna = 0; coluna < COLUNA; coluna++){
            vetor[linha][coluna] = rand() % 10;
            if(linha == coluna){
            	cout << "| " << vetor[linha][coluna] << " |";
			}else{
				cout << "|  |";
			}            
        }
        cout << "\n";
    }
    
    for (int linha = 5; linha > LINHA; linha--){
        for (int coluna = 5; coluna > COLUNA; coluna--){
            vetor[linha][coluna] = rand() % 10;
            if(linha == coluna){
            	cout << "| " << vetor[linha][coluna] << " |";
			}else{
				cout << "| " << vetor[linha][coluna] << " |";
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

    std::cout << "\n";
    std::cout << "\n";
	std::cout << "Soma Diagonais Primarias\n";
    somaDiagonais(vetor);

    std::cout << "\n";
    std::cout << "\n";
	std::cout << "Soma Diagonais Segundarias\n";
    somaDiagonais(vetor);

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
		cout << " = " << linhasSomadas[linha] << "\n";
    }
    return 0;
}

int somaColunas(int vetor[LINHA][COLUNA]){
    // SOMA Diagonais
    int colunasSomadas[5];
    for (int linha = 0; linha < LINHA; linha++){
    	for (int coluna = 0; coluna < COLUNA; coluna++){
    			cout << "| " << vetor[linha][coluna] << " |";  
	    		colunasSomadas[coluna] += vetor[linha][coluna];
				}
		cout << "\n";
	}

	std::cout << "============================\n";
	for (int i = 0; i < 5; i++){
		cout << "| " << colunasSomadas[i] << " |"; 
	}
    return 0;
}

int somaDiagonais(int vetor[LINHA][COLUNA]){
    // SOMA Diagonais
    int diagonaisSomadas[5];
    for (int linha = 0; linha < LINHA; linha++){
    	for (int coluna = 0; coluna < COLUNA; coluna++){
    			cout << "| " << vetor[linha][coluna] << " |";
	    		if(linha == coluna){
	    			cout << "| " << vetor[linha][coluna] << " |";
	    			diagonaisSomadas[coluna] += vetor[linha][coluna];
				}
		}
		cout << "\n";
	}
	std::cout << "____________________________\n";		
	for(int i = 0; i < 1; i++){
		cout << "\n| " << diagonaisSomadas[i] << " |"; 
	}
    return 0;
}

int somaDiagonais2(int vetor[LINHA][COLUNA]){
    // SOMA Diagonais
    int diagonaisSomadas;
    for (int linha = 0; linha < LINHA; linha++){
    	for (int coluna = 0; coluna < COLUNA; coluna++){
    			cout << "| " << vetor[linha][coluna] << " |";
	    		if(linha == coluna){
					cout << "#";
				}else{
	    			diagonaisSomadas = LINHA - 1 - linha;
				}
		}
		cout << "\n";
	}
	std::cout << "____________________________\n";		
	for(int i = 0; i < 1; i++){
		cout << "\n| " << diagonaisSomadas << " |"; 
	}
    return 0;
}
