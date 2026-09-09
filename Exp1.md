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

<img width="972" height="585" alt="image" src="https://github.com/user-attachments/assets/0b4184ad-5f99-4e4b-b693-a4a95af5a56d" />

Result:

Thus, the program is verified successfully.
