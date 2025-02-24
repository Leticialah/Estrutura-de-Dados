# Estrutura-de-Dados
Processamento de imagens

#include <stdio.h>

int busca_sequencial(int tam, int vet[tam], int busca) {
  for(int i = 0; i < tam; i++) {
    if(busca == vet[i]) {
      return i;
    }
  }
  return -1; // não encontrado
}

int busca_binaria(int tam, int vet[tam], int busca) {
  int inicio, meio, fim;
  inicio = 0;
  fim = tam-1;
  meio = (inicio+fim)/2;
  while (inicio <= fim) {
    if(busca == vet[meio]) return meio;
    
    if(busca > vet[meio]) {
      inicio = meio+1;
      continue;
    } else {
      fim = meio-1;
    }
  }
  return -1;
}

int main() {
    int vet[] = {54, 12, 15, 48, 58, 17, 15, 44, 54, 19};
    int vet2[] = {1,2,3,4,6,7,9};
    printf("busca = 15: %d\n", busca_sequencial(10, vet, 15));
    printf("busca = 19: %d\n", busca_sequencial(10, vet, 19));
    printf("busca = 10: %d\n", busca_sequencial(10, vet, 10));
    printf("busca bin: 6 -> %d\n", busca_binaria(7, vet2, 6));
    printf("busca bin: 5 -> %d\n", busca_binaria(7, vet2, 5));
    return 0;
}
