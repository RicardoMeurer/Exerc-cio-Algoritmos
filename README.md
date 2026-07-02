# Exerc-cio-Algoritmos
Calculadora de média em C++
#include <iostream>
#include <string>

using namespace std;


float calcularMedia(float n1, float n2, float n3) {
    return (n1 + n2 + n3) / 3;
}

int main() {

    string nomes[5];
    float nota1[5], nota2[5], nota3[5], medias[5];

    // Entrada dos dados
    for (int i = 0; i < 5; i++) {
        cout << "\nAluno " << i + 1 << endl;

        cout << "Nome: ";
        cin >> nomes[i];

        cout << "Nota 1: ";
        cin >> nota1[i];

        cout << "Nota 2: ";
        cin >> nota2[i];

        cout << "Nota 3: ";
        cin >> nota3[i];

        medias[i] = calcularMedia(nota1[i], nota2[i], nota3[i]);
    }

    
    cout << "\n----- MÉDIA FINAL DOS ALUNOS -----\n";

    for (int i = 0; i < 5; i++) {
        cout << "\nNome: " << nomes[i];
        cout << "\nNotas: " << nota1[i]
             << ", " << nota2[i]
             << ", " << nota3[i];

        cout << "\nMedia: " << medias[i];

        if (medias[i] >= 7)
            cout << "\nSituacao: Aprovado\n";
        else
            cout << "\nSituacao: Reprovado\n";
    }

    
    int indiceMaior = 0;

    for (int i = 1; i < 5; i++) {
        if (medias[i] > medias[indiceMaior]) {
            indiceMaior = i;
        }
    }

    cout << "\nAluno com maior media: "
         << nomes[indiceMaior]
         << " (" << medias[indiceMaior] << ")" << endl;

    return 0;
}
