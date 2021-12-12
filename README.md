# Proyecto-Progg
Proyecto Final

#include <stdio.h>
#include <windows.h>

COORD cxy;
#define posicion(x,y) {(cxy.X)= (x);(cxy.Y)= (y); SetConsoleCursorPosition((GetStdHandle(STD_OUTPUT_HANDLE)), (cxy) );}

char m[][];
char ab=, id=;
char movletra;

void desplazamiento()	
	{
	
		do
		{
			movletra= getch();
			switch(movletra)
				{
					case 119: //w para subir
					posicion(id, ab); 
					printf(" ");
					ab--;
					posicion(id, ab); 
					printf("%c", 254);
					break;
					case 100://d para izquierda
					posicion(id, ab); 
					printf(" ");
					id++;
					posicion(id, ab); 
					printf("%c", 254);
					break;
					case 97://a para derecha
					posicion(id, ab); 
					printf(" ");
					id--;
					posicion(id, ab); 
					printf("%c", 254);
					break;
					case 115://s para bajar
					posicion(id, ab); 
					printf(" ");
					ab++;
					posicion(id, ab); 
					printf("%c", 254);
					break;
				}		
		}
		while(ab!=1);
	
	}
   
   
void laberitno()
{

	int i, j;
	for (i = ; i < ; i++)
	{
		for(j = ; j < ; j++)
		{
			m[i][j]=rand()% ;
		}
	}
}


void mostrarlaberinto()
	{
	
		int i, j;
		for (i = ;i < ;i)
		{
			for(j = ;j < ;j)
			{
				if(m[i][j] < )
				{
					printf(" ");
				}
				else
				{
					printf("%c", 185);
				}
			}
		
		}
	
	}


void coliciones(){

                  }


int main()
{
	
	printf("\tPara moverte utiliza las teclas W para subir %c, S para bajar %c, A para izquierda %c,  D para derecha %c", 24, 25, 27, 26);
	printf("\n\n\n");
	
	srand(time(NULL));
	laberinto();
	mostrarlaberinto();
	posicion(id, ab);
	printf("%c", 254);
	colisiones();
	desplazamiento();

	getch();
	return 0;
}
