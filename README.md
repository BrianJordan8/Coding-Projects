/*
Brian Jordan
Programming in C 
3/10/2023
*/

#include <stdio.h>
#include <math.h>

// prototypes
double readList (double num);
double quadraticFormula (double a, double b, double c);

int main()
{
    double num;
    
    printf("ENTER A LIST OF NUMBERS\n\nSeparate each number by using the Enter Key \n(-1 to stop the list):\n\n");
    
    readList(num);
    
    // Quadratic Equation ---------------------------------------------------------------------------
    double a,b,c;
    
    printf("\nQUADTRATIC EQUATION\n");
    printf("a = ");
    scanf("%lf", &a);
    printf("b = ");
    scanf("%lf", &b);
    printf("c = ");
    scanf("%lf", &c);
    
    quadraticFormula (a,b,c);
    

    return 0;
}

double readList(double num){
    double sum = 0.0, average = 0.0; // average and sum of the numbers
    int count = 0; // counts how many numbers the user entered
    double min, max;
    
    do {
        scanf("%lf", &num);
        
        if (num != -1.0){
            
            if (count == 0) { // if only 1 number has been entered, then max = min
            min = max = num;
            }
            
            if (num > max){
                max = num;
            }
            if (num < min){
                min = num;
            }
            
            count += 1; // adds 1 for every number the user enters
            sum += num; 
            average = sum / count;
            
            
    }
    } while (num != -1.0);
    
    printf("Min = %.2lf\n", min);
    printf("Max = %.2lf\n", max);
    printf("Average = %.2lf\n", average);
    printf("There were %d numbers in the list\n\n", count);
    
}

double quadraticFormula (double a, double b, double c){
    double posAnswer, negAnswer, radicand; // quadratic is always +-
    
    
    radicand = (b * b - (4 * a * c));
    
    
    
    if (radicand < 0) {
        
        radicand = sqrt(radicand * -1);
    
        posAnswer = ((-1 * b)/ (2 * a));
        negAnswer = ((-1 * b)/ (2 * a));
        radicand = radicand / (2 * a);
        printf("\nx1 = %lf + %lfi\n", posAnswer, radicand);
        printf("x2 = %lf - %lfi", posAnswer, radicand);             
    
    }
    else {
        posAnswer = ((-1 * b) + (sqrt(radicand)))/ (2 * a);
        negAnswer = ((-1 * b) - (sqrt(radicand)))/ (2 * a);
        
        printf("\nx1 = %.2lf\n", posAnswer);
        printf("x2 = %.2lf", negAnswer);
    }

}
    









