#include <stdio.h>
#include <string.h>
#include <stdlib.h>

char *ChargerChaine(int N)
{
   char *chaine = (char *) malloc(N * sizeof(char));
    if (chaine != NULL)
    {
        printf("Enter a string : \n");    
        scanf("%s", chaine);
    }  
    return chaine;      
}

int Longueur(char *ch)
{
    int i = 0;
    while (*ch != '\0')
    {
        i++; 
        ch++;
    }    
    return i;
}

void InverserTab(char Tab[], char T[], int m)
{
    int i;
    for ( i = 0 ; i < m ; i++ )
        T[i] = Tab[m-1-i];
    T[m] = '\0';
}

void ChargerTab(char *p, char Tab[])
{
    int i = 0;
    while(*p != '\0')
    {
      Tab[i] = *p;
       i++;
       p++;
    }    
    Tab[i] = '\0';
}

void AfficherTab(char Tab[], int m)
{
    printf("%s\n",Tab);
}

int main()
{
    char *ch;
    int n;
    printf("Veuillez saisir la taille maximale de la chaine : \n");
    scanf("%d", &n);
    ch = ChargerChaine(n);
    printf ("La chaine est : %s\n",ch);
    int m = Longueur(ch);
    printf("La longueur de la chaine est : %d \n",m);
    char Tab[m], T[m];
    ChargerTab(ch, Tab);
    AfficherTab(Tab, m);
    InverserTab(Tab, T, m);
    AfficherTab(T, m);

    free(ch);
    return 0;
}
