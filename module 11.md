# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
   * Step 1.	Include the necessary header #include <stdio.h>.
   * Step 2.	Use a series of if and else if statements to compare the values and return the maximum among them.
   * Step 3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
   * Step 4.	Use scanf to take four integers as input.
   * Step 5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
```C
#include <stdio.h>

// Function to find the greatest of four numbers
int max_of_four(int a, int b, int c, int d) {
    int max = a;
    
    if (b > max)
        max = b;
    if (c > max)
        max = c;
    if (d > max)
        max = d;
    
    return max;
}

int main() {
    int n1, n2, n3, n4, greater;
    
    // Taking input from the user
    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    
    // Calling the function to find the greatest number
    greater = max_of_four(n1, n2, n3, n4);
    
    // Displaying the greatest number
    printf("The greatest number is: %d\n", greater);
    
    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/688a2086-6d03-49be-862e-a50af01080ae)


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
```C
#include <stdio.h>

// Function to calculate the maximum values for AND, OR, and XOR operations
void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    
    // Nested loops to calculate the maximum values for AND, OR, and XOR
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            // AND operation
            if ((i & j) < k && (i & j) > a) {
                a = i & j;
            }
            // OR operation
            if ((i | j) < k && (i | j) > o) {
                o = i | j;
            }
            // XOR operation
            if ((i ^ j) < k && (i ^ j) > x) {
                x = i ^ j;
            }
        }
    }

    // Print the results for AND, OR, and XOR
    printf("Max AND: %d\n", a);
    printf("Max OR: %d\n", o);
    printf("Max XOR: %d\n", x);
}

int main() {
    int n, k;

    // Take inputs from the user
    printf("Enter two integers n and k: ");
    scanf("%d %d", &n, &k);

    // Call the function to calculate the maximum values
    calculate_the_max(n, k);

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/ac96a271-f261-4237-89aa-35d6d9496edb)


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
   * Step 1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
   * Step 2.	Use scanf to take two integers as input for the number of shelves and queries.
   * Step 3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
   * Step 4.	Declare variables k and c to keep track of the book index and the total number of books.
   * Step 5.	Use a for loop to iterate over the queries.
 
## Program:
```C
#include <stdio.h>

int main() {
    int noshel, noque;  // Variables to store number of shelves and number of queries
    int shelarr[50][50], nobookarr[50];  // 2D array for shelves and books, 1D array for book counts
    int k, c, query_type, shelf_no, book_no;

    // Input number of shelves and queries
    printf("Enter the number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    // Initialize the shelves with books (each shelf has no books initially)
    for (int i = 0; i < noshel; i++) {
        nobookarr[i] = 0;  // No books initially
    }

    // Process queries
    for (int i = 0; i < noque; i++) {
        printf("Enter query type (1 for adding books, 2 for counting books on shelf): ");
        scanf("%d", &query_type);

        if (query_type == 1) {  // Add books to a shelf
            printf("Enter shelf number and number of books: ");
            scanf("%d %d", &shelf_no, &k);

            // Add books to the specified shelf
            if (shelf_no <= noshel) {
                shelarr[shelf_no - 1][nobookarr[shelf_no - 1]] = k;
                nobookarr[shelf_no - 1]++;
                printf("%d books added to shelf %d\n", k, shelf_no);
            } else {
                printf("Invalid shelf number!\n");
            }
        }
        else if (query_type == 2) {  // Count total books on a shelf
            printf("Enter shelf number: ");
            scanf("%d", &shelf_no);

            // Count the total number of books on the specified shelf
            if (shelf_no <= noshel) {
                c = 0;
                for (int j = 0; j < nobookarr[shelf_no - 1]; j++) {
                    c += shelarr[shelf_no - 1][j];
                }
                printf("Total books on shelf %d: %d\n", shelf_no, c);
            } else {
                printf("Invalid shelf number!\n");
            }
        } else {
            printf("Invalid query type!\n");
        }
    }

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/d9aff681-bb04-42f0-8023-2e4440b52785)



## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
   * Step 1.	Declare a variable n to store the number of integers.
   * Step 2.	Use scanf to take an integer n as input.
   * Step 3.	Declare an array a of size n to store the integers.
   * Step 4.	Declare a variable sum and initialize it to zero.
   * Step 5.	Use a for loop to iterate n times:
   * Step 6.	Use scanf to input each integer and add it to the sum.
   * Step 7.	Print the final sum using printf.

## Program:
```C
#include <stdio.h>

int main() {
    int n, sum = 0;

    // Step 2: Take number of integers as input
    printf("Enter the number of integers: ");
    scanf("%d", &n);

    int a[n];  // Step 3: Declare an array of size n

    // Step 5: Input elements and calculate sum
    printf("Enter the integers:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];  // Add each element to sum
    }

    // Step 7: Print the final sum
    printf("Sum of the integers in the array = %d\n", sum);

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/5e04588a-2924-4107-800a-e30c2210cca3)


## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

   * Step 1.	Input the sentence: Take a sentence from the user.
   * Step 2.	Initialize a counter variable: This will keep track of the number of words.
   * Step 3.	Process each character of the sentence:
       - Iterate through the sentence, checking each character.
       - If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
   * Step 4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
   * Step 5.	Display the result: After processing the sentence, output the total word count.



## Program:
```C
#include <stdio.h>

int main() {
    char sentence[1000];
    int i = 0, words = 0;
    int inWord = 0; // Flag to check if currently inside a word

    // Step 1: Input the sentence
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // Step 3: Process each character
    while (sentence[i] != '\0') {
        if (sentence[i] != ' ' && sentence[i] != '\n') {
            if (inWord == 0) {
                words++;
                inWord = 1;
            }
        } else {
            inWord = 0;
        }
        i++;
    }

    // Step 5: Display the result
    printf("Number of words in the sentence = %d\n", words);

    return 0;
}


```
## Output:
![image](https://github.com/user-attachments/assets/97d78108-c241-441f-8d67-1101ac02c7d7)



## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
