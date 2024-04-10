# Jogos II (Snake)
## Pensando o Problema

É essencial entendermos o processo que o problema nos propõe. O processo desse problema está na **substituição de valores**, em que substituimos os valores de uma variável por outros.

No enunciado, é dito que precisamos "*criar*" uma cobrinha, definir o tamanho dela e a posição na matriz de cada pedaço da cobrinha. Logo em seguida, precisamos dar comandos de movimentação para essa cobrinha, e movimentá-la na matriz. 

## Dividindo em Partes

Uma forma de facilitar a nossa capacidade de organizar o problema, é **dividindo** ele. Vamos dividi-lo na seguinte maneira:

- **Bloco 1 - Declaração de Variáveis:** nesse primeiro bloco, vamos declarar as principais variáveis que vamos manipular no programa.
- **Bloco 2 - Definição da Cobra:** aqui vamos definir o tamanho da cobra, e a posição de cada pedaço dela.
- **Bloco 3 - Comandos:**  nesse bloco vamos definir quais serão as movimentações da cobra.
- **Bloco 4 - Movimentação:**  vamos fazer o principal processo de movimentação da cobra.
- **Bloco 5 - Impressão:** neste último bloco, vamos imprimir as novas posições do corpo da cobra.
## Código

No **Bloco 1**, primeiramente, vamos definir as nossas variáveis:

	#include <iostream>
	#include <string>

	using namespace std;

	int main(int argc, char** argv) {
	
		//Bloco 1
		int s = 0; //Comprimento da Serpente
		
		int ph[999]; //Posições Horizontais
		int pv[999]; //Posições Verticais
		int recebe_ph = 0;
		int recebe_pv = 0;
		
		int n = 0; //Número de Movimentos;
	
		return 0;
	}

Depois de definir as variáveis, vamos para o **Bloco 2**, em que iremos pedir ao usuário que insira o *Comprimento da Serpente*, e as posições de cada pedaço:

	#include <iostream>
	#include <string>

	using namespace std;

	int main(int argc, char** argv) {
	
		//Bloco 1
		int s = 0; //Comprimento da Serpente
		
		int ph[999]; //Posições Horizontais
		int pv[999]; //Posições Verticais
		
		int recebe_ph = 0;
		int recebe_pv = 0;
		
		int n = 0; //Número de Movimentos;

		//Bloco 2
		cin >> s; //Comprimento da Serpente
		
		//Posições Horizontais
		for(int i = 0; i < s; i++){
			
			cin >> recebe_ph;
			
			ph[i] = recebe_ph;
			
		}
		
		//Posições Verticais
		for(int j = 0; j < s; j++){
			
			cin >> recebe_pv;
			
			pv[j] = recebe_pv;
			
		}	

		return 0;
	}

Agora, no **Bloco 3**, precisamos pedir o número de movimentos e quais serão esses movimentos:

	#include <iostream>
	#include <string>

	using namespace std;

	int main(int argc, char** argv) {
	
		//Bloco 1
		int s = 0; //Comprimento da Serpente
		
		int ph[999]; //Posições Horizontais
		int pv[999]; //Posições Verticais
		
		int recebe_ph = 0;
		int recebe_pv = 0;
		
		int n = 0; //Número de Movimentos;

		//Bloco 2
		cin >> s; //Comprimento da Serpente
		
		//Posições Horizontais
		for(int i = 0; i < s; i++){
			
			cin >> recebe_ph;
			
			ph[i] = recebe_ph;
			
		}
		
		//Posições Verticais
		for(int j = 0; j < s; j++){
			
			cin >> recebe_pv;
			
			pv[j] = recebe_pv;
			
		}	
		
		//Bloco 3
		cin >> n;
	
		string m[n]; //Direção do Move (Letra)
		int mm[n]; //Direção do Move (Numérico)
		
		//Recebendo Direções
		for(int k = 0; k < n; k++){
			
			cin >> m[k];
			
		}	
		
		//Transformando Letra em Número
		for(int h = 0; h < n; h++){
			
			//Cima
			if(m[h] == "c"){
			
				mm[h] = 1;	
			
			}
			
			//Baixo
			if(m[h] == "b"){
			
				mm[h] = 2;	
			
			}
			
			//Direita
			if(m[h] == "d"){
			
				mm[h] = 3;	
			
			}
			
			//Esquerda
			if(m[h] == "e"){
			
				mm[h] = 4;	
			
			}
	
		}		

		return 0;
	}
No **Bloco 4**, será onde movimentaremos a cobra pelo espaço, com um método simples. Usaremos uma estrutura `for` para ler os movimentos. Dentro dessa estrutura, usaremos outra estrutura, o `switch`, para escolhermos a direção em que a cobra se movimentará. O programa vai substituir o corpo e o rabo da cobra para a posição do pedaço posterior, e vai movimentar a cabeça de maneira específica, já que a movimentação parte, primeiramente, da cabeça:

	#include <iostream>
	#include <string>

	using namespace std;

	int main(int argc, char** argv) {
	
		//Bloco 1
		int s = 0; //Comprimento da Serpente
		
		int ph[999]; //Posições Horizontais
		int pv[999]; //Posições Verticais
		
		int recebe_ph = 0;
		int recebe_pv = 0;
		
		int n = 0; //Número de Movimentos;

		//Bloco 2
		cin >> s; //Comprimento da Serpente
		
		//Posições Horizontais
		for(int i = 0; i < s; i++){
			
			cin >> recebe_ph;
			
			ph[i] = recebe_ph;
			
		}
		
		//Posições Verticais
		for(int j = 0; j < s; j++){
			
			cin >> recebe_pv;
			
			pv[j] = recebe_pv;
			
		}	
		
		//Bloco 3
		cin >> n;
	
		string m[n]; //Direção do Move (Letra)
		int mm[n]; //Direção do Move (Numérico)
		
		//Recebendo Direções
		for(int k = 0; k < n; k++){
			
			cin >> m[k];
			
		}	
		
		//Transformando Letra em Número
		for(int h = 0; h < n; h++){
			
			//Cima
			if(m[h] == "c"){
			
				mm[h] = 1;	
			
			}
			
			//Baixo
			if(m[h] == "b"){
			
				mm[h] = 2;	
			
			}
			
			//Direita
			if(m[h] == "d"){
			
				mm[h] = 3;	
			
			}
			
			//Esquerda
			if(m[h] == "e"){
			
				mm[h] = 4;	
			
			}
	
		}

		//Bloco 4
		for(int g = 0; g < n; g++){
			
			//Analisando o movimento da cabeça
			switch (mm[g]){
				
				//Se o movimento for para cima
				case 1:
				for(int f = 0; f < s-1; f++){
					
					//Movimentando o corpo
					pv[f] = pv[f+1];
					ph[f] = ph[f+1]; 
					
				}
				pv[s-1] -= 1;//Movimentando cabeça
				
				break;
				
				//Se o movimento for para baixo
				case 2:
				for(int f_1 = 0; f_1 < s-1;f_1++){
					
					//Movimentando o corpo
					pv[f_1] = pv[f_1+1]; 
					ph[f_1] = ph[f_1+1];
					
				}
				pv[s-1] += 1;//Movimentando cabeça
				
				break;
				
				//Se o movimento for para direita
				case 3:
				for(int f_2 = 0; f_2 < s-1;f_2++){
					
					//Movimentando o corpo
					ph[f_2] = ph[f_2+1]; 
					pv[f_2] = pv[f_2+1];
					
				}
				ph[s-1] += 1;//Movimentando cabeça
				
				break;
				
				//Se o movimento for para esquerda
				case 4:
				for(int f_3 = 0; f_3 < s-1;f_3++){
					
					//Movimentando o corpo
					ph[f_3] = ph[f_3+1]; 
					pv[f_3] = pv[f_3+1];
					
				}
				ph[s-1] -= 1;//Movimentando cabeça
				
				break;
			}
		}	
	
		return 0;
	}
Por fim, no **Bloco 5** , vamos imprimir as posições horizontais e verticais de cada pedaço do corpo, sequencialmente do rabo até a cabeça:

	#include <iostream>
	#include <string>

	using namespace std;

	int main(int argc, char** argv) {
	
		//Bloco 1
		int s = 0; //Comprimento da Serpente
		
		int ph[999]; //Posições Horizontais
		int pv[999]; //Posições Verticais
		
		int recebe_ph = 0;
		int recebe_pv = 0;
		
		int n = 0; //Número de Movimentos;

		//Bloco 2
		cin >> s; //Comprimento da Serpente
		
		//Posições Horizontais
		for(int i = 0; i < s; i++){
			
			cin >> recebe_ph;
			
			ph[i] = recebe_ph;
			
		}
		
		//Posições Verticais
		for(int j = 0; j < s; j++){
			
			cin >> recebe_pv;
			
			pv[j] = recebe_pv;
			
		}	
		
		//Bloco 3
		cin >> n;
	
		string m[n]; //Direção do Move (Letra)
		int mm[n]; //Direção do Move (Numérico)
		
		//Recebendo Direções
		for(int k = 0; k < n; k++){
			
			cin >> m[k];
			
		}	
		
		//Transformando Letra em Número
		for(int h = 0; h < n; h++){
			
			//Cima
			if(m[h] == "c"){
			
				mm[h] = 1;	
			
			}
			
			//Baixo
			if(m[h] == "b"){
			
				mm[h] = 2;	
			
			}
			
			//Direita
			if(m[h] == "d"){
			
				mm[h] = 3;	
			
			}
			
			//Esquerda
			if(m[h] == "e"){
			
				mm[h] = 4;	
			
			}
	
		}

		//Bloco 4
		for(int g = 0; g < n; g++){
			
			//Analisando o movimento da cabeça
			switch (mm[g]){
				
				//Se o movimento for para cima
				case 1:
				for(int f = 0; f < s-1; f++){
					
					//Movimentando o corpo
					pv[f] = pv[f+1];
					ph[f] = ph[f+1]; 
					
				}
				pv[s-1] -= 1;//Movimentando cabeça
				
				break;
				
				//Se o movimento for para baixo
				case 2:
				for(int f_1 = 0; f_1 < s-1;f_1++){
					
					//Movimentando o corpo
					pv[f_1] = pv[f_1+1]; 
					ph[f_1] = ph[f_1+1];
					
				}
				pv[s-1] += 1;//Movimentando cabeça
				
				break;
				
				//Se o movimento for para direita
				case 3:
				for(int f_2 = 0; f_2 < s-1;f_2++){
					
					//Movimentando o corpo
					ph[f_2] = ph[f_2+1]; 
					pv[f_2] = pv[f_2+1];
					
				}
				ph[s-1] += 1;//Movimentando cabeça
				
				break;
				
				//Se o movimento for para esquerda
				case 4:
				for(int f_3 = 0; f_3 < s-1;f_3++){
					
					//Movimentando o corpo
					ph[f_3] = ph[f_3+1]; 
					pv[f_3] = pv[f_3+1];
					
				}
				ph[s-1] -= 1;//Movimentando cabeça
				
				break;
			}	
		
			//Bloco 5
			//Mostrando a Posição Horizontal
			for(int t = 0; t < s; t++){
				
				cout << ph[t] << endl;
				
			}
			
			//Mostrando a Posição Vertical
			for(int tt = 0; tt < s; tt++){
				
				cout << pv[tt] << endl;
				
			}
		
		}
		
		return 0;
	}
Problema Resolvido!
