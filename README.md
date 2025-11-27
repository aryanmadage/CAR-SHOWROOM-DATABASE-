#include <stdio.h>
#include <string.h>


struct Car {
    int number;       
    float price;      
    char model[30];  
};


void bubbleSort(struct Car cars[], int n) {
    struct Car temp;
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (cars[j].price < cars[j+1].price) {
                temp = cars[j];
                cars[j] = cars[j+1];
                cars[j+1] = temp;
            }
        }
    }
}


void displayCars(struct Car cars[], int n) {
    printf("\nCar Information (Sorted by Price, Highest to Lowest):\n");
    printf("-------------------------------------------------------\n");
    printf("Car Number\tModel\t\tPrice\n");
    printf("----------------------------------------\n");
    for (int i = 0; i < n; i++) {
        printf("%d\t\t%s\t\t%.2f\n", cars[i].number, cars[i].model, cars[i].price);
    }
}


int main() {
    struct Car cars[3];


    for (int i = 0; i < 3; i++) {
        printf("Enter details for car %d:\n", i + 1);
        printf("\nEnter car number: ");
        scanf("%d", &cars[i].number);
        printf("\nEnter car model: ");
        scanf("%s", &cars[i].model);
        printf("\nEnter car price: ");
        scanf("%f", &cars[i].price);
        printf("\n");
    }


    bubbleSort(cars, 3);


    displayCars(cars, 3);


    return 0;
}
