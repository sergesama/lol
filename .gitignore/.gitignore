#define _CRT_SECURE_NO_WARNINGS
#include <iostream>
#include <string.h>
#include <cstring>

using namespace std;
int main() {
	setlocale(LC_ALL, "Russian");
	int n;
	cout << "Введите количество строк:";
	cin >> n;
	char** stroka= new char*[n];
	for (int i = 0; i<n; i++)stroka[i] = new char[64];
	cin.getline(stroka[0], 64);
	char* prob=new char[64];
	for (int i = 0; i<64; i++)prob[i] = ' ';
	cout << "Введите строки:"<<endl;
	for (int i = 0; i<n; i++){
		cin.getline(stroka[i], 64);
	}
	cout << "Строки выравненные по правой стороне:" << endl;
	for (int i = 0; i<n; i++){
		int l = strlen(stroka[i]);
		char* prob1 = new char[64];
		strcpy(prob1, prob);
		strcpy(prob1 + (-l + 64), stroka[i]);
		cout << prob1 << endl;
	}
	cout << "Строки выравненные по ширине:" << endl;
	for (int i = 0; i<n; i++){
		int kol_slov = 1;
		int kol_prob_isn = 0;
		if (stroka[i][0] == ' '){
			kol_slov--;
			kol_prob_isn++;
		}
		int l = strlen(stroka[i]);
		for (int j = 1; j < l; j++){
			if (stroka[i][j] != ' ' && stroka[i][j - 1] == ' ')kol_slov++;
			if (stroka[i][j] == ' ')kol_prob_isn++;
		}
		char* prob1 = new char[64];
		strcpy(prob1, prob);
		if (kol_slov == 0)prob1 = " ";
		else if (kol_slov == 1)strcpy(prob1 + (64-l)/2, stroka[i]);
		else{
			int kol_prob = (64 - (l - kol_prob_isn)) / (kol_slov - 1);
			int kol_dobavl_prob = 0;
			int kol_prom = 0;
			for (int j = 0; j < l; j++){
				if (stroka[i][j] != ' '){
					strcpy(prob1 + j - kol_dobavl_prob + kol_prob*kol_prom, stroka[i] + j);
				}
				else{
					for (int k = 1; k <= kol_prob; k++){
						strcpy(prob1 + j + kol_prob*kol_prom+k-1, " ");
					}
					while (stroka[i][j] == ' '&&j < l){
						kol_dobavl_prob++;
						j++;
					}
					j--;
					kol_prom++;
				}
			}
		}
		cout << prob1 << endl;
	}
	system("PAUSE");
}
