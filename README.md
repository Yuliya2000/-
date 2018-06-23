#include <stdio.h>
#include <locale.h>
#include <string.h>
#include "windows.h"
void func(int numb);
char mil(int a, int b, int c, char *str);
char tau(int a1, int b1, int c1, char *str1);
char hun(int a2, int b2, int c2, char *str2);
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
	int pos=0, rest, p, mas[10]={0}, div=1000000000;
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
	tau(mas[4], mas[5], mas[6], s);
	hun(mas[7], mas[8], mas[9], s);
	printf("%s\n", s);	
}
char mil(int a, int b, int c, char *str) {
	int p=strlen(str);
	switch(a) {
		case 1: strcpy(str+p, "сто "); break;
		case 2: strcpy(str+p, "двісті "); break;
		case 3: strcpy(str+p, "триста "); break;
		case 4: strcpy(str+p, "чотириста "); break;
		case 5: strcpy(str+p, "п'ятсот "); break;
		case 6: strcpy(str+p, "шістсот "); break;
		case 7: strcpy(str+p, "сімсот "); break;
		case 8: strcpy(str+p, "вісімсот "); break;
		case 9: strcpy(str+p, "дев'ятсот "); break;
		default: break;
	}
	p=strlen(str);
	switch(b) {
		case 1:
			switch(c) {
				case 0: strcpy(str+p, "десять "); break;
				case 1: strcpy(str+p, "одинадцять "); break;
				case 2: strcpy(str+p, "дванадцять "); break;
				case 3: strcpy(str+p, "тринадцять "); break;
				case 4: strcpy(str+p, "чотирнадцять "); break;
				case 5: strcpy(str+p, "п'ятнадцять "); break;
				case 6: strcpy(str+p, "шістнадцять "); break;
				case 7: strcpy(str+p, "сімнадцять "); break;
				case 8: strcpy(str+p, "вісімнадцять "); break;
				case 9: strcpy(str+p, "дев'ятнадцять "); break;
				default: break;
			}
			c=0; break;
		case 2: strcpy(str+p, "двадцять "); break;
		case 3: strcpy(str+p, "тридцять "); break;
		case 4: strcpy(str+p, "сорок "); break;
		case 5: strcpy(str+p, "п'ятдесят "); break;
		case 6: strcpy(str+p, "шістдесят "); break;
		case 7: strcpy(str+p, "сімдесят "); break;
		case 8: strcpy(str+p, "вісімдесят "); break;
		case 9: strcpy(str+p, "дев'яносто "); break;
			default: break;
	}
	p=strlen(str);
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
char tau(int a1, int b1, int c1, char *str1) {
	int p=strlen(str1);
		switch(a1) {
		case 1: strcpy(str1+p, "сто "); break;
		case 2: strcpy(str1+p, "двісті "); break;
		case 3: strcpy(str1+p, "триста "); break;
		case 4: strcpy(str1+p, "чотириста "); break;
		case 5: strcpy(str1+p, "п'ятсот "); break;
		case 6: strcpy(str1+p, "шістсот "); break; 
		case 7: strcpy(str1+p, "сімсот "); break;
		case 8: strcpy(str1+p, "вісімсот "); break;
		case 9: strcpy(str1+p, "дев'ятсот "); break;
			default: break;
	}
	p=strlen(str1);
	switch(b1) {
		case 1:
			switch(c1) {
				case 0: strcpy(str1+p, "десять "); break;
				case 1: strcpy(str1+p, "одинадцять "); break;
				case 2: strcpy(str1+p, "дванадцять "); break;
				case 3: strcpy(str1+p, "тринадцять "); break;
				case 4: strcpy(str1+p, "чотирнадцять "); break;
				case 5: strcpy(str1+p, "п'ятнадцять "); break;
				case 6: strcpy(str1+p, "шістнадцять "); break;
				case 7: strcpy(str1+p, "сімнадцять "); break;
				case 8: strcpy(str1+p, "вісімнадцять "); break;
				case 9: strcpy(str1+p, "дев'ятнадцять "); break;
					default: break;
			}
			c1=0;	break;
		case 2: strcpy(str1+p, "двадцять "); break;
		case 3: strcpy(str1+p, "тридцять "); break;
		case 4: strcpy(str1+p, "сорок "); break;
		case 5: strcpy(str1+p, "п'ятдесят "); break;
		case 6: strcpy(str1+p, "шістдесят "); break;
		case 7: strcpy(str1+p, "сімдесят "); break;
		case 8: strcpy(str1+p, "вісімдесят "); break;
		case 9: strcpy(str1+p, "дев'яносто "); break;
			default: break;
	}
	p=strlen(str1);
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
	int p=strlen(str2);
		switch(a2) {
	case 1: strcpy(str2+p, "сто "); break;
	case 2: strcpy(str2+p, "двісті "); break;
	case 3: strcpy(str2+p, "триста "); break;
	case 4: strcpy(str2+p, "чотириста "); break;
	case 5: strcpy(str2+p, "п'ятьсот "); break;
	case 6: strcpy(str2+p, "шістсот "); break;
	case 7: strcpy(str2+p, "сімсот "); break;
	case 8: strcpy(str2+p, "вісімсот "); break;
	case 9: strcpy(str2+p, "дев'ятьсот "); break;
	default: break;	
	}
	p=strlen(str2);
	switch(b2) {
	 case 1:
	  	switch(c2) {
	  		case 0: strcpy(str2+p, "десять "); break;
 			case 1: strcpy(str2+p, "одинадцять "); break;
			case 2: strcpy(str2+p, "дванадцять "); break;
			case 3: strcpy(str2+p, "тринадцять "); break;
			case 4: strcpy(str2+p, "чотирнадцять "); break;
			case 5: strcpy(str2+p, "п'ятнадцять "); break;
			case 6: strcpy(str2+p, "шістнадцять "); break;
			case 7: strcpy(str2+p, "сімнадцять "); break;
			case 8: strcpy(str2+p, "вісімнадцять "); break;
			case 9: strcpy(str2+p, "дев'ятнадцять "); break;
				default: break;
					}
		c2=0;	break;
	case 2: strcpy(str2+p, "двадцять "); break;
	case 3: strcpy(str2+p, "тридцять "); break;
	case 4: strcpy(str2+p, "сорок "); break;
	case 5: strcpy(str2+p, "п'ятдесят "); break;
	case 6: strcpy(str2+p, "шістдесят "); break;
	case 7: strcpy(str2+p, "сімдесят "); break;
	case 8: strcpy(str2+p, "вісімдесят "); break;
	case 9: strcpy(str2+p, "дев'яносто "); break;
	default: break;	
	}
	p=strlen(str2);
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
