EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
~~~
#include <stdio.h>

struct eligible {
    int age;
    char n[50];
};

int main() {
    int num_persons, i;

    printf("Enter the number of persons: ");
    scanf("%d", &num_persons);

    struct eligible e[num_persons];

    for(i = 0; i < num_persons; i++) {
        printf("\nEnter details for person %d:\n", i + 1);
        printf("Enter Name: ");
        scanf("%s", e[i].n);
        printf("Enter Age: ");
        scanf("%d", &e[i].age);
    }

    printf("\n--- Vaccine Eligibility Results ---\n");

    for(i = 0; i < num_persons; i++) {
        printf("\nName: %s\n", e[i].n);
        printf("Age: %d\n", e[i].age);

        if (e[i].age <= 6) {
            printf("Vaccine Eligibility: No\n");
        } else {
            printf("Vaccine Eligibility: Yes\n");
        }
    }

    return 0;
}
~~~


Output:

<img width="972" height="585" alt="image" src="https://github.com/user-attachments/assets/c73a8234-eabd-4c45-b85e-66e698f512ec" />



Result:

Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
~~~
#include <stdio.h>

struct numbers {
    int a;
    int b;
};

struct numbers add(struct numbers num);

int main() {
    struct numbers n;
    struct numbers result;

    printf("Enter value for a: ");
    scanf("%d", &n.a);
    
    printf("Enter value for b: ");
    scanf("%d", &n.b);

    result = add(n);

    printf("\n--- Result Returned From Function ---\n");
    printf("Result member a (Sum of a and b): %d\n", result.a);
    printf("Result member b (Copy of original b): %d\n", result.b);

    return 0;
}

struct numbers add(struct numbers num) {
    struct numbers temp;
    
    temp.a = num.a + num.b;
    temp.b = num.b;
    
    return temp;
}

~~~

Output:

<img width="862" height="422" alt="image" src="https://github.com/user-attachments/assets/279f7424-4f18-49de-b8a7-ca516a0fcc39" />


Result:

Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];

    printf("Enter a file name: ");
    scanf("%s", name);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error: Could not create or open the file.\n");
        return 1;
    }

    printf("The file '%s' has been created successfully.\n", name);
    printf("The file has been opened successfully.\n");

    fclose(p);
    printf("The file has been closed.\n");

    return 0;
}
~~~




Output:

<img width="732" height="297" alt="image" src="https://github.com/user-attachments/assets/651df03c-3680-4b77-8d11-a3c07145c2d8" />


Result:

Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
~~~
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];
    char text[200];
    int num;
    int i;

    printf("Enter a file name: ");
    scanf("%s", name);

    printf("Enter the number of strings to insert: ");
    scanf("%d", &num);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error: Could not open or create the file.\n");
        return 1;
    }

    printf("File opened successfully.\n");

    for (i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf("%s", text);
        fputs(text, p);
        fputs("\n", p);
    }

    fclose(p);

    printf("Data has been added successfully.\n");

    return 0;
}
~~~


Output:

<img width="727" height="325" alt="image" src="https://github.com/user-attachments/assets/b73f2b04-0ce0-479f-b09a-dfe71cf02a65" />


Result:

Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
~~~
#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;
    struct subject *s;

    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    s = (struct subject *)malloc(n * sizeof(struct subject));

    if (s == NULL) {
        printf("Memory allocation failed");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("\nEnter details for subject %d:\n", i + 1);

        printf("Enter subject name: ");
        scanf("%s", s[i].name);

        printf("Enter marks: ");
        scanf("%d", &s[i].marks);
    }

    printf("\n--- Student Details ---\n");

    for (i = 0; i < n; i++) {
        printf("\nSubject Name: %s\n", s[i].name);
        printf("Marks: %d\n", s[i].marks);
    }

    free(s);

    return 0;
}
~~~

Output:

<img width="637" height="362" alt="image" src="https://github.com/user-attachments/assets/838ef860-c40c-4a22-8d11-bd3822318e26" />



Result:

Thus, the program is verified successfully
