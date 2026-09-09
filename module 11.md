

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
~~~
#include <stdio.h>

int max_of_four(int n1, int n2, int n3, int n4) {
    int greater;

    if (n1 >= n2 && n1 >= n3 && n1 >= n4)
        greater = n1;
    else if (n2 >= n1 && n2 >= n3 && n2 >= n4)
        greater = n2;
    else if (n3 >= n1 && n3 >= n2 && n3 >= n4)
        greater = n3;
    else
        greater = n4;

    return greater;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("Greatest number = %d\n", greater);

    return 0;
}
~~~

Output:

<img width="612" height="172" alt="Screenshot 2026-09-09 214657" src="https://github.com/user-attachments/assets/2fee1904-6bb8-4125-9ab6-30901a44ab0b" />


Result:

Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
~~~
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int i, j;
    int a = 0, o = 0, x = 0;

    for (i = 1; i <= n; i++) {
        for (j = i + 1; j <= n; j++) {
            if ((i & j) < k && (i & j) > a)
                a = i & j;

            if ((i | j) < k && (i | j) > o)
                o = i | j;

            if ((i ^ j) < k && (i ^ j) > x)
                x = i ^ j;
        }
    }

    printf("Maximum AND = %d\n", a);
    printf("Maximum OR = %d\n", o);
    printf("Maximum XOR = %d\n", x);
}

int main() {
    int n, k;

    printf("Enter the values of n and k: ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
~~~

Output:


<img width="550" height="230" alt="image" src="https://github.com/user-attachments/assets/44bd09a6-f8dd-49d0-9a7a-a84714f2faf2" />


Result:

Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

int main() {
    int noshel, noque;
    int **shelarr;
    int *nobookarr;
    int k, c = 0;
    int i, j;

    printf("Enter the number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    shelarr = (int **)malloc(noshel * sizeof(int *));
    nobookarr = (int *)calloc(noshel, sizeof(int));

    for (i = 0; i < noshel; i++)
        shelarr[i] = NULL;

    for (i = 0; i < noque; i++) {
        int type, x, y;

        scanf("%d %d %d", &type, &x, &y);

        if (type == 1) {
            k = nobookarr[x];

            shelarr[x] = (int *)realloc(shelarr[x], (k + 1) * sizeof(int));
            shelarr[x][k] = y;

            nobookarr[x]++;
        } else if (type == 2) {
            printf("%d\n", shelarr[x][y]);
        } else if (type == 3) {
            printf("%d\n", nobookarr[x]);
        }
    }

    for (i = 0; i < noshel; i++)
        free(shelarr[i]);

    free(shelarr);
    free(nobookarr);

    return 0;
}
~~~

Output:

<img width="730" height="237" alt="image" src="https://github.com/user-attachments/assets/a1f8dc61-918b-427a-851a-d6223aaa0c86" />


Result:

Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
~~~
#include <stdio.h>

int main() {
    int n, i, sum = 0;
    int a[100];

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    printf("Enter the integers:\n");

    for (i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum = sum + a[i];
    }

    printf("Sum of the integers = %d\n", sum);

    return 0;
}
~~~

Output:

<img width="620" height="327" alt="image" src="https://github.com/user-attachments/assets/d69a550e-8317-43eb-903e-0d7696c309f0" />


Result:

Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
~~~
#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[200];
    int i = 0;
    int count = 0;
    int inWord = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if (isspace(sentence[i])) {
            inWord = 0;
        } else if (inWord == 0) {
            count++;
            inWord = 1;
        }

        i++;
    }

    printf("Number of words = %d\n", count);

    return 0;
}
~~~

Output:

<img width="747" height="217" alt="image" src="https://github.com/user-attachments/assets/b3d7da01-0a9c-45a2-a534-d37a0ecbe49d" />


Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
