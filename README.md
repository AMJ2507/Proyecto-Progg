# Proyecto-Progg
Proyecto Final

#include <stdio.h>
#include<conio.h>
#include <windows.h>


COORD cxy;
#define posicion(x,y) {(cxy.X)= (x);(cxy.Y)= (y); SetConsoleCursorPosition((GetStdHandle(STD_OUTPUT_HANDLE)), (cxy) );}

char m[20][80];
char ab=2, id=0;
char movletra;

void desplazamiento()
	{
	
		do
		{
			movletra= getch();
			switch(movletra)
				{
					case 119: //w
					posicion(id, ab); 
					printf(" ");
					ab--;
					posicion(id, ab); 
					printf("%c", 254);
					break;
					case 100://d
					posicion(id, ab); 
					printf(" ");
					id++;
					posicion(id, ab); 
					printf("%c", 254);
					break;
					case 97://a
					posicion(id, ab); 
					printf(" ");
					id--;
					posicion(id, ab); 
					printf("%c", 254);
					break;
					case 115://s
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

//Genero valores aleatorios para todas las posiciones de mi arreglo bidimensional m  
void laberinto()
	{
		int i, j;
		for(i=0;i<20;i++)
		{
			for(j=0;j<40;j++)
			{
				m[i][j]=rand()%100;
			}
		}
	}

/*dibuja el laberinto diciendo que para cualquier posición
del arreglo m donde el valor que se le ha asignado aleatoriamente
sea menor que 65, me aparezca como un espacio en blanco, y el resto 
de valores que imprima los caracteres indicados ╣ ║ ╗ ╝ ╚ ╔ ╩ ╦ ╠ ═ ╬ */
void mostrarlaberinto()
	{
	
		int i, j;
		for (i=0;i<20;i++)
		{
			for(j=0;j<80;j++)
			{
				if(m[i][j] < 65)
				{
					printf(" ");
				}
				else
				{
        			printf("%c", 186);
				}
			}
		
		}
	
	}


void colisiones()
	{

	}
	


int main()
{
	
	printf("\tPara moverte utiliza las teclas W para subir %c, S para bajar %c, A para izquierda %c,  D para derecha %c", 24, 25, 27, 26);
	printf("\n\n\n");
	
	laberinto();
	mostrarlaberinto();
	posicion(id, ab);
	printf("%c", 254);
	colisiones();
	desplazamiento();


	
	getch();
	return 0;	
	
}
