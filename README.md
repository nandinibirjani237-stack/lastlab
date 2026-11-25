# lastlab
# task 1
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int n,m,i;
    int *reg;

    printf("enter number of students ");
    scanf("%d", &n);

    reg = (int *)malloc(n * sizeof(int));
    if (reg == NULL) {
        printf("not allocated\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("enter registration number %d",i + 1);
        scanf("%d", &reg[i]);
    }

    printf("\nstudent registration numbers\n");
    for (i = 0; i < n; i++)
        printf("%d\n", reg[i]);

    printf("\nenter number of new students");
    scanf("%d", &m);

    reg = (int *)realloc(reg, (n + m) * sizeof(int));
    if (reg == NULL) {
        printf("not reallocated\n");
        return 1;
    }

    for (i = n; i < n + m; i++) {
        printf("enter registration number %d",i + 1);
        scanf("%d", &reg[i]);
    }

    printf("\nupdated registration numbers\n");
    for (i = 0; i < n + m; i++)
        printf("%d\n", reg[i]);

    free(reg);
    # task 2
    #include <stdio.h>
#include <stdlib.h>

int main()
{
    int n, i;
    int *roll;
    float *marks;
    float sum = 0, avg;

    printf("enter number of students");
    scanf("%d", &n);

    roll = (int *)calloc(n,sizeof(int));
    marks = (float *)calloc(n,sizeof(float));
    if (roll == NULL||marks == NULL) {
        printf("memory not allocated\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("\nenter roll number of student %d",i + 1);
        scanf("%d", &roll[i]);
        printf("enter marks of student %d",i + 1);
        scanf("%f", &marks[i]);
        sum = sum + marks[i];
    }

    avg = sum/n;

    printf("\nrollno\tmarks\n");
    for (i = 0; i < n; i++)
        printf("%d %f\n",roll[i],marks[i]);

    printf("\naverage marks = %f\n",avg);

    free(roll);
    free(marks);
    return 0;
}
# task 3
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int n, m, i;
    float *price;
    float total = 0;

    printf("how many products do you want to buy: ");
    scanf("%d", &n);

    price = (float *)malloc(n * sizeof(float));
    if (price == NULL) {
        printf("memory not allocated\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("enter price of product %d", i + 1);
        scanf("%f", &price[i]);
    }

    printf("\nhow many more products do you want to add");
    scanf("%d", &m);

    price = (float *)realloc(price, (n + m) * sizeof(float));
    if (price == NULL) {
        printf("memory not reallocated\n");
        return 1;
    }

    for (i = n; i < n + m; i++) {
        printf("enter price of product %d", i + 1);
        scanf("%f", &price[i]);
    }

    printf("\nproduct prices\n");
    for (i = 0; i < n + m; i++) {
        printf("product %d %.2f\n", i + 1, price[i]);
        total = total + price[i];
    }

    printf("\n bill = %f\n", total);

    free(price);
    return 0;
}

    return 0;
}
