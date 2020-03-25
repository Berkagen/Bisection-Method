#include <stdio.h>
#include <math.h>

double function(double x)
{
    return pow(x, 3) + 4 * pow(x, 2) - 10;
}

double calculateAn(double a1, double b1)
{
    double p = a1 + (b1 - a1) / 2;
    if (function(p) > 0 && function(a1) > 0 || function(p) < 0 && function(a1) < 0)
    {
        a1 = p;
        return a1;
    }

    else
    {
        return a1;
    }
}

double calculateBn(double a1, double b1)
{
    double p = a1 + (b1 - a1) / 2;
    if (function(p) > 0 && function(a1) > 0 || function(p) < 0 && function(a1) < 0)
    {
        return b1;
    }

    else
    {
        b1 = p;
        return b1;
    }
}

int main()
{
    double chart[20][20];
    double a1 = 1.0;
    double b1 = 2.0;
    int i = 0;
    int j = 0;
    int n = 0;

    printf("n\t\tAn\t\tBn\t\tPn\t\tF(Pn)\t\trelative error\n");

    for (i = 0; i < 20; i++)
    {
        for (j = 0; j < 5; j++)
        {
            printf("%d\t\t", n + 1); //printing the n values
            n++;
            j++;

            if (i == 0)
            {
                chart[i][j] = a1;
                printf("%lf\t", chart[i][j]);
                j++;

                chart[i][j] = b1;
                printf("%lf\t", chart[i][j]);
                j++;
            }

            else
            {
                chart[i][j] = calculateAn(a1, b1); //printing the An values
                printf("%lf\t", chart[i][j]);
                j++;

                chart[i][j] = calculateBn(a1, b1); //printing the Bn values
                printf("%lf\t", chart[i][j]);
                j++;

                if (a1 != calculateAn(a1, b1))
                {
                    a1 = calculateAn(a1, b1);
                }

                if (b1 != calculateBn(a1, b1))
                {
                    b1 = calculateBn(a1, b1);
                }
            }

            chart[i][j] = (a1 + b1) / 2.0; //printing the Pn values
            printf("%lf\t", chart[i][j]);
            j++;

            chart[i][j] = function((a1 + b1) / 2.0); //printing the F(Pn) values
            printf("%lf\t", chart[i][j]);
            j++;

            if (i == 0) //printing the relative error values
            {
                chart[i][j] = fabs(chart[i][j - 2] - a1) / fabs(chart[i][j - 2]); // There is a special occasion for first relative error.
                printf("%lf", chart[i][j]);
            }
            chart[i][j] = fabs(chart[i][j - 2] - chart[i - 1][j - 2]) / fabs(chart[i][j - 2]);
            printf("%lf", chart[i][j]);

            if (chart[i][j] < 0.001) //breaking the for loop
            {
                goto here;
            }
        }
        printf("\n");
    }
    here:
    return 0;
}

