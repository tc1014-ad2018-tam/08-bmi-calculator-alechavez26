# 08-bmi-calculator-alechavez26
08-bmi-calculator-alechavez26 created by GitHub Classroom
/*This program calculates a person's Body Mass Index.
 * Alejandra Chávez   Cruz
 * 13/sept/2018
 * A01411970@itesm.mx
 *
 *
 */

 #include <stdio.h>
#include <math.h>

//This function calculates IBM in metrical system
int metricSystem(double kg, double m) {
    double metric = (kg / (m * m));
    return metric;

}

//This Function calculates the IBM in imperial System
int imperialSystem(double p, double ft){
    double result,kg,m;
    kg=(p*0.453592);
    m=(ft*0.3048);
    result=kg/(m*m);
    return  result;
}

void menu(){
    printf("\n1. Metric Units");
    printf("\n2. Imperial units\n");
}


int main() {
    //Declare the variables
    int option;
    double w;
    double h;
    double BMI;


    printf("This program will calculate your BMI \n");
    printf("What system would you like to use? \n");

    menu();

    scanf("%i",&option);
    switch(option){

        case 1:

            do{
                printf("\nGive me your height in Meters");
                scanf("%lf", &h);
            }while(h<=0);

            printf("\nGive me your weight in Kilograms");
            scanf("%lf",&w);

            BMI=metricSystem(w,h);
            printf("\nYour IBM is: %lf \n",BMI);
            break;

        case 2:

            do{
                printf("\nGive me your height in fts please");
                scanf("%lf", &h);
            }while(h<=0);

            printf("\nGive me your weight in Pounds please");
            scanf("%lf",&w);

            BMI=imperialSystem(w,h);
            printf("\nYour BMI is: %lf \n",BMI);
            break;

        default:

            printf("oh no, that´s not valid");
            break;
    }

    return 0;
}
