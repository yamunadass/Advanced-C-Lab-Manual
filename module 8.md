# EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
## Aim:
To write a C program print the lowercase English word corresponding to the number
## Algorithm:
   * Step 1. Initialize an integer variable n.
   * Step 2.	Input Validation
   * Step 3.	Switch Statement cases.
     -	Case 5: Print "seventy one"
     -	Case 6: Print "seventy two"
     -	Case 13: Print "seventy three"
     -	...
     -	Case 13: Print "seventy nine"
     -	Default: Print "Greater than 13"
   * Step 4.	Exit the program.
 
## Program:
```C
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 13:
            printf("seventy three\n");
            break;
        case 79:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0;
}

```
## Output:


![image](https://github.com/user-attachments/assets/d6824179-6f0f-4100-ab87-e8804c0a2542)



## Result:
Thus, the program is verified successfully
 
# EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS  IN A SINGLE LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
## Algorithm:
   * Step 1.	Start
   * Step 2.	Declare char array a[50] outer loop for each digit from 0 to 3
   * Step 3.	Initialize counter c to 0
   * Stpe 4.	For each character in the string print count c for current digit, followed by a space
   * Step 5.	Increment h to move to the next digit
   * Step 6.	End
 
## Program:
```C
#include <stdio.h>

int main() {
    char a[50];
    int i, c[4] = {0, 0, 0, 0}; // Counter for digits 0, 1, 2, 3

    printf("Enter a string: ");
    scanf("%s", a);

    for(i = 0; a[i] != '\0'; i++) {
        if(a[i] == '0') {
            c[0]++;
        } else if(a[i] == '1') {
            c[1]++;
        } else if(a[i] == '2') {
            c[2]++;
        } else if(a[i] == '3') {
            c[3]++;
        }
    }

    // Print the frequency of digits 0, 1, 2, and 3
    for(i = 0; i < 4; i++) {
        printf("%d ", c[i]);
    }
    printf("\n");

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/59c86506-20c8-4e86-9205-e6d237212b5d)

## Result:
Thus, the program is verified successfully

# EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
   * Step 1.	Start
   * Step 2.	Declare variables s (pointer to an array of strings) and n (number of strings)
   * Step 3.	Memory Allocation
     - Dynamically allocate memory for s to store an array of strings
   * Step 4.	Input
     - Read the number of strings n from the user Dynamically allocate memory for each string in s
   * Step 5.	Permutation Generation Loop
   * Step 6.	Memory Deallocation
     - Free the memory allocated for each string in s Free the memory allocated for s
   * Step 7.	End
 
## Program:
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to swap two characters in a string
void swap(char* x, char* y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to generate and print all permutations of a string
void permute(char* str, int left, int right) {
    if (left == right) {
        printf("%s\n", str);  // Print the permutation
    } else {
        for (int i = left; i <= right; i++) {
            swap((str + left), (str + i));  // Swap characters
            permute(str, left + 1, right);  // Recursively generate permutations
            swap((str + left), (str + i));  // Backtrack and restore the string
        }
    }
}

int main() {
    char* str;
    int n;

    // Input the number of strings (length of string)
    printf("Enter the string: ");
    str = (char*)malloc(100 * sizeof(char));  // Dynamically allocate memory for the string
    scanf("%s", str);

    int length = strlen(str);
    
    // Sort the string in lexicographical order to generate permutations in order
    qsort(str, length, sizeof(char), (int (*)(const void*, const void*)) strcmp);

    // Print all permutations of the string
    printf("All permutations in lexicographical order:\n");
    permute(str, 0, length - 1);

    // Free the allocated memory
    free(str);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/ba473bea-56c7-46b6-a951-798196269ec4)


## Result:
Thus, the program is verified successfully
 
# EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS SHOWN BELOW.
## Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
## Algorithm:
   * Step 1.	Start
   * Step 2.	Declare integer variables n, i, j, min
   * Step 3.	Read the value of n from the user
   * Step 4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
   * Step 5.	Matrix Generation Loop
   * Step 6.	Calculate min as the minimum distance to the borders
   * Step 7.	End
 
## Program:
```C
#include <stdio.h>

int main() {
    int n, i, j, len, min;
    
    // Step 3: Read the value of n from the user
    printf("Enter the value of n: ");
    scanf("%d", &n);
    
    // Step 4: Calculate the length of the side of the square matrix
    len = 2 * n - 1;
    
    // Step 5: Matrix Generation Loop
    for(i = 0; i < len; i++) {
        for(j = 0; j < len; j++) {
            // Step 6: Calculate min as the minimum distance to the borders
            min = (i < j) ? i : j;
            min = (min < len - i - 1) ? min : len - i - 1;
            min = (min < len - j - 1) ? min : len - j - 1;
            
            // Print the number based on the min value
            printf("%d ", n - min);
        }
        printf("\n");
    }
    
    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/be98c2f3-80d8-458e-8e01-cf2ecfa8afea)


## Result:
Thus, the program is verified successfully

# EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:
   * Step 1.	Start.
   * Step 2.	Define a function square() with no parameters. This function will return an integer value.
   * Step 3.	Inside the function:
     -	Declare an integer variable to store the number.
     -	Ask the user to input a number.
     -	Calculate the square of the number (multiply the number by itself).
     -	Return the squared value.
   * Step 4.	In the main function:
     - Call the square() function and display the result.
   * Step 5. End.

## Program:
```C
#include <stdio.h>

// Step 2: Define function square() with no arguments
int square() {
    int num;
    
    // Step 3: Ask user for input
    printf("Enter a number: ");
    scanf("%d", &num);
    
    // Calculate and return the square
    return num * num;
}

int main() {
    int result;
    
    // Step 4: Call the square() function and display the result
    result = square();
    
    printf("Square of the number: %d\n", result);
    
    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/1b947d79-a647-477a-a9a3-08b1377db604)

## Result:
Thus, the program is verified successfully
