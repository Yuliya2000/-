#include <stdio.h>
#include <locale.h>
#include <string.h>
#include "windows.h"
void func(int numb);
char mil(int a, int b, int c, char *str);
char thoy(int a1, int b1, int c1, char *str1);
char hun(int a2, int b2, int c2, char *str2);
char pr(int l, int k, int &j, char *st); 
int main() {
	int num;
		SetConsoleCP(1251);
SetConsoleOutputCP(1251); 
setlocale(LC_CTYPE, "ukr");
	printf("Введіть ціле число:");
	scanf("%i", &num);
	if(num==0) printf("Нуль\n");
		if(num<0) {
		printf("Мінус ");
		num=num*(-1);	
		} 
		func(num);
	return 0;
}
void func(int numb) {
	char s[100]={0}; 
	int  rest, p, mas[10]={0}, div=1000000000;
	for (int i = 0; i < 10; i++) {
    rest = (int)(numb / div);
    mas[i] = rest;
    p=rest*div;
    numb = numb-p;
    div =div/ 10;
 }
	switch(mas[0]) {
		case 1: strcpy(s, "Один мільярд "); break;
		case 2: strcpy(s, "Два мільярди "); break;
		default: break;
	}	
	mil(mas[1], mas[2], mas[3], s);
	thoy(mas[4], mas[5], mas[6], s);
	hun(mas[7], mas[8], mas[9], s);
	printf("%s\n", s);	
}
char mil(int a, int b, int c, char *str) {
	pr(a, b, c, str);
	int p=strlen(str);
	switch(c) {
		case 1: strcpy(str+p, "один мільйон "); break;
		case 2: strcpy(str+p, "два мільйони "); break;
		case 3: strcpy(str+p, "три мільйони "); break;
		case 4: strcpy(str+p, "чотири мільйони "); break;
		case 5: strcpy(str+p, "п'ять мільйонів "); break;
		case 6: strcpy(str+p, "шість мільйонів "); break;
		case 7: strcpy(str+p, "сім мільйонів "); break;
		case 8: strcpy(str+p, "вісім мільйонів "); break;
		case 9: strcpy(str+p, "дев'ять мільйонів "); break;
			default: if(a!=0||b!=0) strcpy(str+p, "мільйонів "); break;
	}
	return *str;
}
char thoy(int a1, int b1, int c1, char *str1) {
	pr(a1, b1, c1, str1);
	int p=strlen(str1);
	switch(c1) {
		case 1: strcpy(str1+p, "одна тисяча "); break;
		case 2: strcpy(str1+p, "дві тисячи "); break; 
		case 3: strcpy(str1+p, "три тисячи "); break;
		case 4: strcpy(str1+p, "чотири тисячи "); break;
		case 5: strcpy(str1+p, "п'ять тисяч "); break; 
		case 6: strcpy(str1+p, "шість тисяч "); break;
		case 7: strcpy(str1+p, "сім тисяч "); break;
		case 8: strcpy(str1+p, "вісім тисяч "); break;
		case 9: strcpy(str1+p, "дев'ять тисяч "); break;
			default: if(a1!=0||b1!=0) strcpy(str1+p, "тисяч "); break;
	}
	return *str1;
}
char hun(int a2, int b2, int c2, char *str2) {
    pr(a2, b2, c2, str2);
	int p=strlen(str2);
	switch(c2) {
		case 1: strcpy(str2+p, "один "); break;
		case 2: strcpy(str2+p, "два "); break;
		case 3: strcpy(str2+p, "три "); break;
		case 4: strcpy(str2+p, "чотири "); break;
		case 5: strcpy(str2+p, "п'ять "); break;
		case 6: strcpy(str2+p, "шість "); break;
		case 7: strcpy(str2+p, "сім "); break;
		case 8: strcpy(str2+p, "вісім "); break;
		case 9: strcpy(str2+p, "дев'ять "); break;
		default: break;
	}
}
char pr(int l, int k, int &j, char *st) {
		int p=strlen(st);
		switch(l) {
	case 1: strcpy(st+p, "сто "); break;
	case 2: strcpy(st+p, "двісті "); break;
	case 3: strcpy(st+p, "триста "); break;
	case 4: strcpy(st+p, "чотириста "); break;
	case 5: strcpy(st+p, "п'ятьсот "); break;
	case 6: strcpy(st+p, "шістсот "); break;
	case 7: strcpy(st+p, "сімсот "); break;
	case 8: strcpy(st+p, "вісімсот "); break;
	case 9: strcpy(st+p, "дев'ятьсот "); break;
	default: break;	
	}
	p=strlen(st);
	switch(k) {
	 case 1:
	  	switch(j) {
	  		case 0: strcpy(st+p, "десять "); break;
 			case 1: strcpy(st+p, "одинадцять "); break;
			case 2: strcpy(st+p, "дванадцять "); break;
			case 3: strcpy(st+p, "тринадцять "); break;
			case 4: strcpy(st+p, "чотирнадцять "); break;
			case 5: strcpy(st+p, "п'ятнадцять "); break;
			case 6: strcpy(st+p, "шістнадцять "); break;
			case 7: strcpy(st+p, "сімнадцять "); break;
			case 8: strcpy(st+p, "вісімнадцять "); break;
			case 9: strcpy(st+p, "дев'ятнадцять "); break;
				default: break;
					}
		j=0;	break;
	case 2: strcpy(st+p, "двадцять "); break;
	case 3: strcpy(st+p, "тридцять "); break;
	case 4: strcpy(st+p, "сорок "); break;
	case 5: strcpy(st+p, "п'ятдесят "); break;
	case 6: strcpy(st+p, "шістдесят "); break;
	case 7: strcpy(st+p, "сімдесят "); break;
	case 8: strcpy(st+p, "вісімдесят "); break;
	case 9: strcpy(st+p, "дев'яносто "); break;
	default: break;	
	}
	return *st;
}
