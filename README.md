# py1
#include <stdio.h>

void mergeSortedArrays(int arr1[], int size1, int arr2[], int size2, int mergedArr[]) {
    int i = 0, j = 0, k = 0;
    
    while (i < size1 && j < size2) {
        if (arr1[i] <= arr2[j]) {
            mergedArr[k++] = arr1[i++];
        } else {
            mergedArr[k++] = arr2[j++];
        }
    }
    
    while (i < size1) {
        mergedArr[k++] = arr1[i++];
    }
    
    while (j < size2) {
        mergedArr[k++] = arr2[j++];
    }
}

int main() {
    const int MAX_SIZE = 100;
    int size1, size2;
    int arr1[MAX_SIZE], arr2[MAX_SIZE], mergedArr[MAX_SIZE * 2];
    
    scanf("%d", &size1);
    for (int i = 0; i < size1; i++) {
        scanf("%d", &arr1[i]);
    }
    
    scanf("%d", &size2);
    for (int i = 0; i < size2; i++) {
        scanf("%d", &arr2[i]);
    }

    mergeSortedArrays(arr1, size1, arr2, size2, mergedArr);

    for (int i = 0; i < size1 + size2; i++) {
        printf("%d ", mergedArr[i]);
    }
    printf("\n");

    return 0;
}
