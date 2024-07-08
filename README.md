# Практична 8 
Виконав: Печкур Максим
# Опис
Тема: анаграма

Анаграмою слова називають перестановку всіх букв слова. Наприклад зі слова SOLO можна отримати 12 анаграм: SOLO, LOSO, OSLO, OLSO, OSOL, OLOS, SLOO, OOLS, OOSL, LOOS, SOOL. напишіть програму, яка виводитиме кількість анаграм , які можуть вийти зі слова. 

Вхідні дані: в одному рядку задане слово, кількість букв якого не перевищує 14.

Вихідні дані: кількість можливих анаграм.
# Код
```
#include <stdio.h>
#include <string.h>
int factorial(int n) {
    int result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}

int lich(char word[16] , char B){
    int ans=0;
    
     for (int i = 0; i < strlen(word); i++) {
        if (word[i] == B) {
            ans++;
        }
    }
    
    return ans;
}

int anagram (char word[16]){
    
    int len = strlen(word);
    int an = 0;
    int od = 1;
    
    for(int i = 0; i<len;i++){
    
    for(int j = i+1; j <len ;j++){
    
    if(word[i] == word[j]){
            
        od *= factorial(lich(word, word[j]));    
        }    
        
    }
    
    }
 
    an= factorial(len)/od;
 
    return an;
}


int main()
{   char word[16];
    
    
    printf("Введіть слово до 14 букв -  ");
    scanf("%s", word);
    
    
    int amount = anagram(word);
    
    
    printf("Ваше слово - %s\nКількість анаграм - %d", word , amount);
    return 0;
}
```
