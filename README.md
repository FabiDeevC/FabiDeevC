#include<stdlib.h>
#include<stdio.h>
#include<conio.h>
#include<string.h>
struct lista_dobleSchool
{
int matricula;
char semestre[100];;
char Nombre[100];
char carrera[100];
char Tutor [100];
char Gestor[100];
char Facultad [100];
char campus[100];
char direccion[100];
char gene[100];
struct lista_dobleSchool*LadoIzq;
struct lista_dobleSchool*LadoDer;
};
//variables globales

struct lista_dobleSchool*inicio;
struct lista_dobleSchool*nuevo;
struct lista_dobleSchool*fin;
struct lista_dobleSchool*aux;
struct lista_dobleSchool *ant;
struct lista_dobleSchool *fin;
struct lista_dobleSchool *act;

int valor;
void menu(void);
void inicio_insertarLista(void);
void Imprimir_LadoDer(void);
void Imprimir_LadoIzq(void);
void finaal(void);
void BuscarLista(void);
void ModificarLista(void);
void Eliminarlista(void);

int main()
{
	inicio = NULL;
    fin = NULL;
    nuevo=NULL;

	menu();
	system("PAUSE");
	return 0;
}
void menu(){
	int opcion, dato;
		inicio = NULL;
	do{
		printf("\n            |-------------------------------------------------------------------------------|");
		printf("\n            |                             Lista Doble  (Escuela)                            |");
        printf("\n            |-------------------------------------------------------------------------------|");
         printf("\n|----------------------------------------------------------------------------------------------------------------|");
		printf("\n |1.-Ingresar datos a la lista al inicio            | 2. Mostrar datos  ld                                        |");
		printf("\n |3.-Motrar datos li                                | 4.- Buscar                                                  |");
		printf("\n |5.-Modificar                                      | 6.- Eliminar                                                |");
		printf("\n |7. Final                                          | 8.- Salir                                                   |");
		printf("\n |--------------------------------------------------|------------------------------------------------------------ |");
		printf("\n\nInserte un numero que desee (tabla): ");

		printf("\n\tOpcion: ");
		scanf("%d", &opcion);

		switch(opcion){

            case 1:
			  		inicio_insertarLista();
					printf("\n");
					system("PAUSE");
					break;

			case 2:
				 	Imprimir_LadoDer();
					printf("\n");
					system("PAUSE");
					break;

			case 3:
                    Imprimir_LadoIzq();
					printf("\n");
					system("PAUSE");
					break;
            case 4:
					BuscarLista();
					printf("\n");
					system("PAUSE");
					break;
            case 5:
                    ModificarLista();
					printf("\n");
					system("PAUSE");
					break;

            case 6:
                    Eliminarlista();
					printf("\n");
					system("PAUSE");
					break;

			case 7:
					finaal();
					printf("\n");
					system("PAUSE");
					break;




		}
		system("cls");
	}while(opcion != 8);

}

////Insertar al inicio/////////////////////

void inicio_insertarLista(){
        printf("\n\n");
		inicio = NULL;
        nuevo=(struct lista_dobleSchool*)malloc(sizeof (struct lista_dobleSchool));
        printf("\n- Ingrese matricula:");
		scanf("%d",&nuevo->matricula);
		fflush(stdin);
		if(nuevo->matricula>0){
        printf("\n-Ingrese el semestre que cursas actualmente(Primer semestre, segudo semestre...):");
        gets(nuevo->semestre);
          printf("\n-Ingrese nombre completo:");
		gets(nuevo->Nombre);


		printf("\n-Ingrese nombre de su carrera:");
		gets(nuevo->carrera);


		printf("\n-Ingrese nombre de su Facultad: ");
		gets(nuevo->Facultad);


		printf("\n-Ingrese nombre de su Tutor: ");
		gets(nuevo->Tutor);


		printf("-Ingrese nombre de su Gestor: ");
		gets(nuevo->Gestor);


        fflush(stdin);
        printf("Ingrese en que campus te encuentras (Campus I / Campus III ):  ");
		gets(nuevo->campus);


		fflush(stdin);
        printf("Ingrese su direccion:  ");
		gets(nuevo->direccion);



		fflush(stdin);
        printf("Ingrese su Generacion:  ");
		gets(nuevo->gene);

	}
    printf("\n\n");
    while(nuevo->matricula>0){

			if(inicio==NULL){
		inicio=nuevo;
		fin=nuevo;
		nuevo->LadoIzq=NULL;
		nuevo->LadoDer=NULL;

		}
		else
		{
		    nuevo->LadoDer=inicio;
			inicio->LadoIzq=nuevo;
			inicio=nuevo;
			nuevo->LadoIzq=NULL;
		}
        nuevo=(struct lista_dobleSchool *)malloc(sizeof (struct lista_dobleSchool));
        printf("\n\nda una matricula:");
        scanf("%d", &nuevo->matricula);
        fflush(stdin);
        if (nuevo->matricula > 0)
        {
		printf("\n-Ingrese el semestre que cursas actualmente(Primer semestre, segudo semestre...):");
        gets(nuevo->semestre);

        printf("\n-Ingrese nombre completo:");
		gets(nuevo->Nombre);
		getchar();

		printf("\n-Ingrese nombre de su carrera:");
		gets(nuevo->carrera);
        getchar();

		printf("\n-Ingrese nombre de su Facultad: ");
		gets(nuevo->Facultad);
		getchar();

		printf("\n-Ingrese nombre de su Tutor: ");
		gets(nuevo->Tutor);
		getchar();

		printf("-Ingrese nombre de su Gestor: ");
		gets(nuevo->Gestor);
		getchar();

        fflush(stdin);
        printf("Ingrese en que campus te encuentras (Campus I / Campus III ):  ");
		gets(nuevo->campus);
		getchar();

		fflush(stdin);
        printf("Ingrese su direccion:  ");
		gets(nuevo->direccion);
		getchar();


		fflush(stdin);
        printf("Ingrese su Generacion:  ");
		gets(nuevo->gene);
		getchar();

	}

}
printf("\n\n");
}




///////////////////////////////// Insertar al final //////////////////////////

void finaal(void){
printf("\n\n");

		nuevo=(struct lista_dobleSchool *)malloc(sizeof (struct lista_dobleSchool));
		printf("Da una matricula: ");
			scanf("%d",&nuevo->matricula);
	fflush(stdin);

		if(nuevo->matricula>0){
		printf("\n-Ingrese el semestre que cursas actualmente(Primer semestre, segudo semestre...):");
        gets(nuevo->semestre);

        printf("\n-Ingrese nombre completo:");
		gets(nuevo->Nombre);
		getchar();

		printf("\n-Ingrese nombre de su carrera:");
		gets(nuevo->carrera);
        getchar();

		printf("\n-Ingrese nombre de su Facultad: ");
		gets(nuevo->Facultad);
		getchar();

		printf("\n-Ingrese nombre de su Tutor: ");
		gets(nuevo->Tutor);
		getchar();

		printf("-Ingrese nombre de su Gestor: ");
		gets(nuevo->Gestor);
		getchar();

        fflush(stdin);
        printf("Ingrese en que campus te encuentras (Campus I / Campus III ):  ");
		gets(nuevo->campus);
		getchar();

		fflush(stdin);
        printf("Ingrese su direccion:  ");
		gets(nuevo->direccion);
		getchar();


		fflush(stdin);
        printf("Ingrese su Generacion:  ");
		gets(nuevo->gene);
		getchar();
			}
while(nuevo->matricula>0){

			if(inicio==NULL){
		fin=nuevo;
		inicio=nuevo;
		nuevo->LadoIzq=NULL;
		nuevo->LadoDer=NULL;

		}else{
			nuevo->LadoDer=NULL;
			nuevo->LadoIzq=fin;
			fin->LadoDer=nuevo;
			fin=nuevo;
}

		nuevo=(struct lista_dobleSchool *)malloc(sizeof (struct lista_dobleSchool));
			printf("\nDa una matricula: ");
			scanf("%d",&nuevo->matricula);
			if(nuevo->matricula>0){
fflush(stdin);
	printf("\n-Ingrese el semestre que cursas actualmente(Primer semestre, segudo semestre...):");
        gets(nuevo->semestre);

        printf("\n-Ingrese nombre completo:");
		gets(nuevo->Nombre);
		getchar();

		printf("\n-Ingrese nombre de su carrera:");
		gets(nuevo->carrera);
        getchar();

		printf("\n-Ingrese nombre de su Facultad: ");
		gets(nuevo->Facultad);
		getchar();

		printf("\n-Ingrese nombre de su Tutor: ");
		gets(nuevo->Tutor);
		getchar();

		printf("-Ingrese nombre de su Gestor: ");
		gets(nuevo->Gestor);
		getchar();

        fflush(stdin);
        printf("Ingrese en que campus te encuentras (Campus I / Campus III ):  ");
		gets(nuevo->campus);
		getchar();

		fflush(stdin);
        printf("Ingrese su direccion:  ");
		gets(nuevo->direccion);
		getchar();


		fflush(stdin);
        printf("Ingrese su Generacion:  ");
		gets(nuevo->gene);
		getchar();


		}


	}printf("\n\n");
}




////////////////////////// Mostrar lista Inicio (ld) ////////////////////////////////

void Imprimir_LadoDer(void)
{
	aux=inicio;
	while(aux!=NULL){
		printf("\n| ****************   |  ****************|");
        printf("\n| - Matricula: %d  ",aux->matricula);
        printf("\n| - Nombre: %s    ",aux->Nombre); //
        printf("\n| - Carrera:%s   ",aux->carrera);
        printf("\n| - Tutor: %s     ",aux->Tutor);
        printf("\n| - Gestor: %s     ",aux->Gestor);
        printf("\n| - Facultad: %s  ",aux->Facultad);
        printf("\n| - Campus: %s    ",aux->campus);
        printf("\n| - Semestre: %s   ",aux->carrera);
        printf("\n| - Direccion: %s  ",aux->direccion);
        printf("\n| ****************   |  ****************|");
        printf("\n\n");
		aux=aux->LadoDer;
	}

}


////////////////////////// Mostrar lista final (li) ////////////////////////////////

void Imprimir_LadoIzq(void)
{
aux=fin;
		while(aux!=NULL)
            {
        printf("\n| ****************   |  ****************|");
        printf("\n| - Matricula: %d  ",aux->matricula);
        printf("\n| - Nombre: %s    ",aux->Nombre); //
        printf("\n| - Carrera:%s   ",aux->carrera);
        printf("\n| - Tutor: %s     ",aux->Tutor);
        printf("\n| - Gestor: %s     ",aux->Gestor);
        printf("\n| - Facultad: %s  ",aux->Facultad);
        printf("\n| - Campus: %s    ",aux->campus);
        printf("\n| - Semestre: %s   ",aux->carrera);
        printf("\n| - Direccion: %s  ",aux->direccion);
        printf("\n| ****************   |  ****************|");
        printf("\n\n");

		aux=aux->LadoIzq;
    }
}
/////////////BUSQUEDA////////////////
void BuscarLista(void)
{
  printf("Escribe matricuala a BUSCAR:");
	scanf("%d",&valor);
	if(inicio==NULL)
		printf("lista vacía");
	else  //si la lista no esta vacía
	{	aux=inicio;
		if(aux->matricula==valor)
      {// esta en la primer posición
        printf("\n| ****************   |  ****************|");
        printf("\n| - Matricula: %d  ",aux->matricula);
        printf("\n| - Nombre: %s    ",aux->Nombre); //
        printf("\n| - Carrera:%s   ",aux->carrera);
        printf("\n| - Tutor: %s     ",aux->Tutor);
        printf("\n| - Gestor: %s     ",aux->Gestor);
        printf("\n| - Facultad: %s  ",aux->Facultad);
        printf("\n| - Campus: %s    ",aux->campus);
        printf("\n| - Semestre: %s   ",aux->carrera);
        printf("\n| - Direccion: %s  ",aux->direccion);
        printf("\n| ****************   |  ****************|");
     }

else      //esta a partir de la segunda posición
			while(aux->matricula!=valor && aux!=NULL)
         			{
			aux=aux->LadoDer;
			if(aux->matricula==valor)
        printf("\n| ****************   |  ****************|");
        printf("\n| - Matricula: %d  ",aux->matricula);
        printf("\n| - Nombre: %s    ",aux->Nombre); //
        printf("\n| - Carrera:%s   ",aux->carrera);
        printf("\n| - Tutor: %s     ",aux->Tutor);
        printf("\n| - Gestor: %s     ",aux->Gestor);
        printf("\n| - Facultad: %s  ",aux->Facultad);
        printf("\n| - Campus: %s    ",aux->campus);
        printf("\n| - Semestre: %s   ",aux->carrera);
        printf("\n| - Direccion: %s  ",aux->direccion);
        printf("\n| ****************   |  ****************|");

                	 	}
	}


}

////////MODIFICAR///////////
void ModificarLista(void){
	aux = inicio;
	int valor = 0, encontrado = 0;
	printf(" Ingrese el dato del nodo a Buscar para Modificar: ");
	scanf("%d", &valor);
	if(inicio!=NULL){
		while(aux != NULL && encontrado != 1){

			if(aux->matricula == valor){
				printf("\n El nodo con el dato ( %d ) Encontrado", valor);
            printf("\n\nda la nueva matricula:");
          scanf("%d", &aux->matricula);
          fflush(stdin);
          printf("\n-Ingrese el semestre que cursas actualmente(Primer semestre, segudo semestre...):");
        gets(nuevo->semestre);

        printf("\n-Ingrese nombre completo:");
		gets(nuevo->Nombre);


		printf("\n-Ingrese nombre de su carrera:");
		gets(nuevo->carrera);


		printf("\n-Ingrese nombre de su Facultad: ");
		gets(nuevo->Facultad);


		printf("\n-Ingrese nombre de su Tutor: ");
		gets(nuevo->Tutor);


		printf("-Ingrese nombre de su Gestor: ");
		gets(nuevo->Gestor);


        fflush(stdin);
        printf("Ingrese en que campus te encuentras (Campus I / Campus III ):  ");
		gets(nuevo->campus);


		fflush(stdin);
        printf("Ingrese su direccion:  ");
		gets(nuevo->direccion);



		fflush(stdin);
        printf("Ingrese su Generacion:  ");
		gets(nuevo->gene);
		printf("\n Nodo modificado con exito\n\n");
				encontrado = 1;
			}
			aux = aux->LadoDer;
		}
		if(encontrado == 0){
			printf("\n Nodo no Encontrado\n\n");
		}
	}else{
		printf("\n La lista se encuentra vacia\n\n");
	}

}
/////////////ELIMINAR///////////////////
void Eliminarlista(void)
{
aux =inicio;
ant=NULL;
int valor = 0, encontrado = 0;
printf(" Ingrese el dato del nodo a Buscar para Eliminar: ");
	scanf("%d", &valor);

	if(inicio!=NULL){
		while(aux != NULL && encontrado != 1){

			if(aux->matricula == valor){

				if(aux==inicio){
					inicio = inicio->LadoDer;
					inicio->LadoIzq = NULL;
				}else if(aux==fin){
					ant->LadoDer = NULL;
					fin = ant;
				}else{
					ant->LadoDer = aux->LadoDer;
					aux->LadoDer->LadoIzq = ant;
				}
				printf("\n Nodo eliminado con exito\n\n");

				encontrado = 1;
			}
			ant = aux;
			aux = aux->LadoDer;
		}
		if(encontrado == 0){
			printf("\n Nodo no Encontrado\n\n");
		}else{
			free(ant);
		}
	}else{
		printf("\n La lista se encuentra vacia\n\n");
	}

}
