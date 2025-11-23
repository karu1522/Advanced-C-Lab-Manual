# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```c
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d)
        return a;
    else if (b >= a && b >= c && b >= d)
        return b;
    else if (c >= a && c >= b && c >= d)
        return c;
    else
        return d;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("Greatest number = %d\n", greater);
}
```

## Output:
<img width="310" height="75" alt="image" src="https://github.com/user-attachments/assets/551c58c5-cadd-432c-86d1-5f642768e4c3" />


## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
# EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
```c
#include <stdio.h>
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;

    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {

            int and_val = i & j;
            int or_val  = i | j;
            int xor_val = i ^ j;

            if (and_val < k && and_val > a)
                a = and_val;
            if (or_val < k && or_val > o)
                o = or_val;
            if (xor_val < k && xor_val > x)
                x = xor_val;
        }
    }
    printf("%d\n%d\n%d\n", a, o, x);
}

int main() {
    int n, k;
    printf("Enter n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
}
```


## Output:
<img width="249" height="111" alt="image" src="https://github.com/user-attachments/assets/ccecffaa-be1d-44d7-bfb9-ad596520dba9" />


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
```c
#include <stdio.h>
#include <stdlib.h>
int main() {
    int nsh, nqu;
    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &nsh, &nqu);

    int *nobook = (int *)malloc(nsh * sizeof(int));
    int **shel = (int **)malloc(nsh * sizeof(int *));

    for (int i = 0; i < nsh; i++) {
        nobook[i] = 0;
        shel[i] = (int *)malloc(1000 * sizeof(int));
    }

    for (int q = 0; q < nqu; q++) {
        int type;
        printf("\nEnter query type (1-Add, 2-Get, 3-Count): ");
        scanf("%d", &type);

        if (type == 1) {
            int x, y;
            printf("Enter shelf number and book number: ");
            scanf("%d %d", &x, &y);
            shel[x][nobook[x]++] = y;
        } else if (type == 2) {
            int x, y;
            printf("Enter shelf number and book index: ");
            scanf("%d %d", &x, &y);
            if (y < nobook[x])
                printf("Book at shelf %d, index %d: %d\n", x, y, shel[x][y]);
            else
                printf("Invalid book index.\n");
        } else if (type == 3) {
            int x;
            printf("Enter shelf number: ");
            scanf("%d", &x);
            printf("Number of books on shelf %d: %d\n", x, nobook[x]);
        } else {
            printf("Invalid query type.\n");
        }
    }

    for (int i = 0; i < nsh; i++)
        free(shel[i]);
    free(shel);
    free(nobook);
}
```

## Output:
<img width="417" height="199" alt="image" src="https://github.com/user-attachments/assets/064a76cb-08ae-4ee0-8b59-11e9b8759c55" />


## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:
```c
#include <stdio.h>
int main() {
    int n, sum = 0;
    printf("Enter number of iteration: ");
    scanf("%d", &n);
    int a[n];
    for (int i = 0; i < n; i++) {
        printf("%d. : ",i+1);
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("%d", sum);
}
```

## Output:
<img width="286" height="133" alt="image" src="https://github.com/user-attachments/assets/19a28503-3812-4efb-bb7a-b4260a22d7b3" />


 


## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


  
# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE



## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
```c
#include <stdio.h>
int main() {
    char s[200];
    int count = 0, i = 0;
    printf("Enter a sentence : ");
    fgets(s, sizeof(s), stdin);
    while (s[i] != '\0') {
        if ((s[i] != ' ' && s[i] != '\n') &&
            (i == 0 || s[i-1] == ' ')) {
            count++;
        }
        i++;
    }
    printf("Number of words in sentence is : %d", count);
}
```

## Output:
<img width="386" height="73" alt="image" src="https://github.com/user-attachments/assets/52cf557f-1dd2-4953-a794-c88ef5c17e34" />




## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
