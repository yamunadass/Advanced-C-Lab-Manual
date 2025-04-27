## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

## Aim:

To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:
   * Step 1: Declare structure eligible with age (integer) and n (character array)
   * Step 2:	Declare variable e of type eligible
   * Step 3: Input age and name using scanf, store in e
   * Step 4: If e.age <= 6
             Print "Vaccine Eligibility: No"
             Else
             Print "Vaccine Eligibility: Yes"
   * Step 5: Print details (e.age, e.n)
   * Step 6: Return 0

## Program:
```C
#include <stdio.h>

struct eligible {
    int age;
    char n[50];
};

int main() {
    int i, num;
    
    printf("Enter number of persons: ");
    scanf("%d", &num);
    
    struct eligible e[num];
    
    for(i = 0; i < num; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", e[i].n);
        
        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &e[i].age);
    }
    
    printf("\n--- Vaccine Eligibility Check ---\n");
    
    for(i = 0; i < num; i++) {
        printf("\nName: %s\n", e[i].n);
        printf("Age: %d\n", e[i].age);
        
        if(e[i].age > 6) {
            printf("Vaccine Eligibility: Yes\n");
        } else {
            printf("Vaccine Eligibility: No\n");
        }
    }
    
    return 0;
}

```


## Output:
![image](https://github.com/user-attachments/assets/1003533b-50e8-42fa-9967-3fbacd157a8b)



## Result:
Thus, the program is verified successfully. 



## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
## Aim:
To write a C program for passing structure as function and returning a structure from a function

## Algorithm:
   * Step 1:	Define structure numbers with members a and b.
   * Step 2: Declare variable n of type numbers.
   * Step 3: Prompt the user to enter values for a and b.
   * Step 4: Input values for a and b into n using scanf.
   * Step 5:	Call the add function with n as an argument.
   * Step 6: Print the result returned by the add function.
   * Step 7: Return 0
 
## Program:
```C
#include <stdio.h>

struct numbers {
    int a;
    int b;
};

struct numbers add(struct numbers n) {
    struct numbers result;
    result.a = n.a + n.b;
    return result;
}

int main() {
    struct numbers n, sum;
    
    printf("Enter two numbers:\n");
    scanf("%d %d", &n.a, &n.b);
    
    sum = add(n);
    
    printf("Sum = %d\n", sum.a);
    
    return 0;
}


```


## Output:

![image](https://github.com/user-attachments/assets/8f8e69ab-43bb-4e4f-b041-2851211f5590)


## Result:
Thus, the program is verified successfully


 
## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

## Aim:
To write a C program to read a file name from user

## Algorithm:
   * Step 1: Include the necessary header file stdio.h.
   * Step 2: Begin the main function.
   * Step 3:	Declare a file pointer p.
   * Step 4: Declare a character array name to store the file name.
   * Step 5: Prompt the user to enter a file name.
   * Step 6: Use scanf to input the file name into the name array.
   * Step 7: Print a message indicating that the file with the specified name has been created successfully.
   * Step 8: Use fopen to open a file with the name provided by the user in write mode ("w").
   * Step 9: If successful, continue to the next step.
   * Step 10:If unsuccessful, print an error message and exit the program with a non-zero status.
   * Step 11:Print a message indicating that the file has been opened successfully.
   * Step 12:Use fclose to close the file.
   * Step 13:Print a message indicating that the file has been closed.
   * Step 14:End the main function.
   * Step 15:Return 0 to indicate successful program execution.
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100];
    
    printf("Enter the file name to create: ");
    scanf("%s", name);
    
    p = fopen(name, "w");
    
    if (p == NULL) {
        printf("Error opening file!\n");
        return 1; // Non-zero return indicates failure
    }
    
    printf("File '%s' created and opened successfully.\n", name);
    
    fclose(p);
    
    printf("File '%s' closed successfully.\n", name);
    
    return 0;
}


```


## Output:
![image](https://github.com/user-attachments/assets/a817c695-7c49-4efd-9254-0e05b7e0b604)


## Result:
Thus, the program is verified successfully
 


## EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
## Aim:
To write a C program to read, a file and insert text in that file
## Algorithm:
   * Step 1.	Include the necessary header file stdio.h.
   * Step 2.	Begin the main function.
   * Step 3. Declare a file pointer p and declare character arrays name and text and declare an integer variable num.
   * Step 4.	Prompt the user to enter a file name and the number of strings.
   * Step 5. Use scanf to input the file name into the name array and the number of strings into the num variable.
   * Step 6. Use fopen to open a file with the name provided by the user in write mode ("w").
     -	If successful, continue to the next step.
     -	If unsuccessful, print an error message and exit the program with a non-zero status.
   * Step 7. Print a message indicating that the file has been opened successfully.
   * Step 8. Use a loop to input strings from the user and write them to the file using fputs.
   * Step 9. Use fclose to close the file.
   * Step 10. Print a message indicating that data has been added successfully.
   * Step 11. End the main function.
   * Step 12. Return 0 to indicate successful program execution.
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *p;
    char name[100], text[200];
    int num, i;
    
    printf("Enter the file name to create and write into: ");
    scanf("%s", name);
    
    printf("Enter the number of lines you want to insert: ");
    scanf("%d", &num);
    
    p = fopen(name, "w");
    
    if (p == NULL) {
        printf("Error opening file!\n");
        return 1; // Non-zero return indicates failure
    }
    
    printf("File '%s' opened successfully.\n", name);
    
    printf("Enter the text lines:\n");
    for(i = 0; i < num; i++) {
        printf("Line %d: ", i + 1);
        scanf(" %[^\n]", text); // To read a line with spaces
        fputs(text, p);
        fputs("\n", p); // Add a new line after each string
    }
    
    fclose(p);
    
    printf("Data written to '%s' successfully.\n", name);
    
    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/0970ab34-bc98-4111-bcf1-760068eb05cf)


## Result:
Thus, the program is verified successfully



## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

## Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

## Algorithm:
   * Step 1.Input the number of subjects.
   * Step 2.Read the integer value n from the user, which represents the number of subjects.
   * Step 3.Dynamically allocate memory:
   * Step 4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).
   * Step 5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.
   * Step 6.Input the details of each subject
   * Step 7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.
   * Step 8.Display the details of each subject
   * Step 9.Use another for loop to print the name and marks of each subject.
   * Step 10.Free the allocated memory
   * Step 11.After all operations are done, call free(s) to release the dynamically allocated memory.
   * Step 12.Return from the main function
   * Step 13.End the program by returning 0.

## Program:
```C
#include <stdio.h>
#include <stdlib.h>

struct Subject {
    char name[50];
    int marks;
};

int main() {
    struct Subject *s;
    int n, i;
    
    printf("Enter the number of subjects: ");
    scanf("%d", &n);
    
    s = (struct Subject *)malloc(n * sizeof(struct Subject));
    
    if (s == NULL) {
        printf("Memory allocation failed!\n");
        return 1; // Non-zero return indicates failure
    }
    
    for (i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf("%s", s[i].name);
        printf("Enter marks for subject %d: ", i + 1);
        scanf("%d", &s[i].marks);
    }
    
    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: %s, Marks: %d\n", i + 1, s[i].name, s[i].marks);
    }
    
    free(s);
    
    return 0;
}


```

## Output:
![Screenshot 2025-04-27 165440](https://github.com/user-attachments/assets/57d61d17-e9e6-47c1-9cf0-c6306c66f76c)


## Result:
Thus, the program is verified successfully
