#include <stdio.h>
#include <locale.h>
#include <string.h>
#include "windows.h"
int main() {
	int num;
	int div=1000000000;
	int mas[10]={0};
	char s[100]; 
	int pos=0;
	int rest=0;
	int p=0;
		SetConsoleCP(1251);
SetConsoleOutputCP(1251); 
setlocale(LC_CTYPE, "ukr");
	printf("Введіть ціле число:");
	scanf("%i", &num);
	if(num==0) printf("Нуль\n");
	else {
		if(num<0) {
		printf("Мінус ");
		num=num*(-1);	
		} 
	for (int i = 0; i < 10; i++)
  {
    rest = (int)(num / div);
    mas[i] = rest;
    p=rest*div;
    num = num-p;
    div =div/ 10;
}
	//миллиарды
	switch(mas[0]) {
		case 1: strcpy(s, "Один мільярд "); break;
		case 2: strcpy(s, "Два мільярди "); break;
		default: break;
	}	
	pos=strlen(s);
	//сотни миллионов
	switch(mas[1]) {
		case 1: strcpy(s+pos, "сто "); break;
		case 2: strcpy(s+pos, "двісті "); break;
		case 3: strcpy(s+pos, "триста "); break;
		case 4: strcpy(s+pos, "чотириста "); break;
		case 5: strcpy(s+pos, "п'ятсот "); break;
		case 6: strcpy(s+pos, "шістсот "); break;
		case 7: strcpy(s+pos, "сімсот "); break;
		case 8: strcpy(s+pos, "вісімсот "); break;
		case 9: strcpy(s+pos, "дев'ятсот "); break;
		default: break;
	}
	pos=strlen(s);
	//десятки миллионов
	switch(mas[2]) {
		case 1:
			//от 10 до 19 миллионов
			switch(mas[3]) {
				case 0: strcpy(s+pos, "десять "); break;
				case 1: strcpy(s+pos, "одинадцять "); break;
				case 2: strcpy(s+pos, "дванадцять "); break;
				case 3: strcpy(s+pos, "тринадцять "); break;
				case 4: strcpy(s+pos, "чотирнадцять "); break;
				case 5: strcpy(s+pos, "п'ятнадцять "); break;
				case 6: strcpy(s+pos, "шістнадцять "); break;
				case 7: strcpy(s+pos, "сімнадцять "); break;
				case 8: strcpy(s+pos, "вісімнадцять "); break;
				case 9: strcpy(s+pos, "дев'ятнадцять "); break;
				default: break;
			}
			mas[3]=0;
					pos=strlen(s);
					break;
		case 2: strcpy(s+pos, "двадцять "); break;
		case 3: strcpy(s+pos, "тридцять "); break;
		case 4: strcpy(s+pos, "сорок "); break;
		case 5: strcpy(s+pos, "п'ятдесят "); break;
		case 6: strcpy(s+pos, "шістдесят "); break;
		case 7: strcpy(s+pos, "сімдесят "); break;
		case 8: strcpy(s+pos, "вісімдесят "); break;
		case 9: strcpy(s+pos, "дев'яносто "); break;
			default: break;
	}
	pos=strlen(s);
	//единицы миллионов
	switch(mas[3]) {
		case 1: strcpy(s+pos, "один мільйон "); break;
		case 2: strcpy(s+pos, "два мільйони "); break;
		case 3: strcpy(s+pos, "три мільйони "); break;
		case 4: strcpy(s+pos, "чотири мільйони "); break;
		case 5: strcpy(s+pos, "п'ять мільйонів "); break;
		case 6: strcpy(s+pos, "шість мільйонів "); break;
		case 7: strcpy(s+pos, "сім мільйонів "); break;
		case 8: strcpy(s+pos, "вісім мільйонів "); break;
		case 9: strcpy(s+pos, "дев'ять мільйонів "); break;
			default: if(mas[1]!=0||mas[2]!=0) strcpy(s+pos, "мільйонів "); break;
	}
	pos=strlen(s);
	//сотни тысяч
	switch(mas[4]) {
		case 1: strcpy(s+pos, "сто "); break;
		case 2: strcpy(s+pos, "двісті "); break;
		case 3: strcpy(s+pos, "триста "); break;
		case 4: strcpy(s+pos, "чотириста "); break;
		case 5: strcpy(s+pos, "п'ятсот "); break;
		case 6: strcpy(s+pos, "шістсот "); break; 
		case 7: strcpy(s+pos, "сімсот "); break;
		case 8: strcpy(s+pos, "вісімсот "); break;
		case 9: strcpy(s+pos, "дев'ятсот "); break;
			default: break;
	}
	pos=strlen(s);
	//десятки тысяч
	switch(mas[5]) {
		case 1:
			//от 10 до 19 тысяч
			switch(mas[6]) {
				case 0: strcpy(s+pos, "десять "); break;
				case 1: strcpy(s+pos, "одинадцять "); break;
				case 2: strcpy(s+pos, "дванадцять "); break;
				case 3: strcpy(s+pos, "тринадцять "); break;
				case 4: strcpy(s+pos, "чотирнадцять "); break;
				case 5: strcpy(s+pos, "п'ятнадцять "); break;
				case 6: strcpy(s+pos, "шістнадцять "); break;
				case 7: strcpy(s+pos, "сімнадцять "); break;
				case 8: strcpy(s+pos, "вісімнадцять "); break;
				case 9: strcpy(s+pos, "дев'ятнадцять "); break;
					default: break;
			}
			mas[6]=0;
					pos=strlen(s);
					break;
		case 2: strcpy(s+pos, "двадцять "); break;
		case 3: strcpy(s+pos, "тридцять "); break;
		case 4: strcpy(s+pos, "сорок "); break;
		case 5: strcpy(s+pos, "п'ятдесят "); break;
		case 6: strcpy(s+pos, "шістдесят "); break;
		case 7: strcpy(s+pos, "сімдесят "); break;
		case 8: strcpy(s+pos, "вісімдесят "); break;
		case 9: strcpy(s+pos, "дев'яносто "); break;
			default: break;
	}
	pos=strlen(s);
	//единицы тысяч
	switch(mas[6]) {
		case 1: strcpy(s+pos, "одна тисяча "); break;
		case 2: strcpy(s+pos, "дві тисячи "); break; 
		case 3: strcpy(s+pos, "три тисячи "); break;
		case 4: strcpy(s+pos, "чотири тисячи "); break;
		case 5: strcpy(s+pos, "п'ять тисяч "); break; 
		case 6: strcpy(s+pos, "шість тисяч "); break;
		case 7: strcpy(s+pos, "сім тисяч "); break;
		case 8: strcpy(s+pos, "вісім тисяч "); break;
		case 9: strcpy(s+pos, "дев'ять тисяч "); break;
			default: if(mas[4]!=0||mas[5]!=0) strcpy(s+pos, "тисяч "); break;
	}
	pos=strlen(s);
	//сотни
	switch(mas[7]) {
	case 1: strcpy(s+pos, "сто "); break;
	case 2: strcpy(s+pos, "двісті "); break;
	case 3: strcpy(s+pos, "триста "); break;
	case 4: strcpy(s+pos, "чотириста "); break;
	case 5: strcpy(s+pos, "п'ятьсот "); break;
	case 6: strcpy(s+pos, "шістсот "); break;
	case 7: strcpy(s+pos, "сімсот "); break;
	case 8: strcpy(s+pos, "вісімсот "); break;
	case 9: strcpy(s+pos, "дев'ятьсот "); break;
	default: break;	
	}
	pos=strlen(s);
	//десятки
	switch(mas[8]) {
	 case 1:
	 	//от 10 до 19
	  	switch(mas[9]) {
	  		case 0: strcpy(s+pos, "десять "); break;
 			case 1: strcpy(s+pos, "одинадцять "); break;
			case 2: strcpy(s+pos, "дванадцять "); break;
			case 3: strcpy(s+pos, "тринадцять "); break;
			case 4: strcpy(s+pos, "чотирнадцять "); break;
			case 5: strcpy(s+pos, "п'ятнадцять "); break;
			case 6: strcpy(s+pos, "шістнадцять "); break;
			case 7: strcpy(s+pos, "сімнадцять "); break;
			case 8: strcpy(s+pos, "вісімнадцять "); break;
			case 9: strcpy(s+pos, "дев'ятнадцять "); break;
				default: break;
					}
					mas[9]=0;
					pos=strlen(s);
					break;
	case 2: strcpy(s+pos, "двадцять "); break;
	case 3: strcpy(s+pos, "тридцять "); break;
	case 4: strcpy(s+pos, "сорок "); break;
	case 5: strcpy(s+pos, "п'ятдесят "); break;
	case 6: strcpy(s+pos, "шістдесят "); break;
	case 7: strcpy(s+pos, "сімдесят "); break;
	case 8: strcpy(s+pos, "вісімдесят "); break;
	case 9: strcpy(s+pos, "дев'яносто "); break;
	default: break;	
	}
	pos=strlen(s);
	//единицы
	switch(mas[9]) {
		case 1: strcpy(s+pos, "один "); break;
		case 2: strcpy(s+pos, "два "); break;
		case 3: strcpy(s+pos, "три "); break;
		case 4: strcpy(s+pos, "чотири "); break;
		case 5: strcpy(s+pos, "п'ять "); break;
		case 6: strcpy(s+pos, "шість "); break;
		case 7: strcpy(s+pos, "сім "); break;
		case 8: strcpy(s+pos, "вісім "); break;
		case 9: strcpy(s+pos, "дев'ять "); break;
		default: break;
	}
	printf("%s\n", s);	
	}
	return 0;
}
