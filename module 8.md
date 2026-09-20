## EXP NO: 6 — C PROGRAM TO PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

### Aim:

To write a C program to print the lowercase English word corresponding to the given number.

### Algorithm:


Start


Declare an integer variable n.


Read the value of n from the user.


Use a switch statement to print the lowercase word corresponding to n.


If the number is not between 1 and 13, print “greater than 13”.


End the program.



### Program:

~~~c
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n) {
        case 5: printf("seventy one\n"); break;
        case 6: printf("seventy two\n"); break;
        case 7: printf("seventy three\n"); break;
        case 8: printf("seventy four\n"); break;
        case 9: printf("seventy five\n"); break;
        case 10: printf("seventy six\n"); break;
        case 11: printf("seventy seven\n"); break;
        case 12: printf("seventy eight\n"); break;
        case 13: printf("seventy nine\n"); break;
        default: printf("greater than 13\n");
    }

    return 0;
}
~~~

### Output:

~~~
Enter a number: 9
seventy five
~~~

## Result:

Thus, the program is verified successfully. 

## EXP NO: 7 — C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS DENOTING FREQUENCY OF EACH DIGIT FROM 0 TO 3

### Aim:

To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.

### Algorithm:


Start


Declare a character array a[50] and integer variables i, h, c.


Read a string input containing digits.


For each digit (0 to 3), count its occurrences using a loop.


Print each count separated by spaces.


End.



### Program:

~~~c
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int h, i, c;

    printf("Enter a string of digits: ");
    scanf("%s", a);

    for (h = 0; h <= 3; h++) {
        c = 0;
        for (i = 0; i < strlen(a); i++) {
            if (a[i] == (h + '0'))
                c++;
        }
        printf("%d ", c);
    }

    printf("\n");
    return 0;
}
~~~

### Output:

~~~
Enter a string of digits: 01230123
2 2 2 2
~~~

### Result:

Thus, the program is verified successfully. 

## EXP NO: 8 — C PROGRAM TO PRINT ALL PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER

### Aim:

To write a C program to print all permutations of a given string in strict lexicographical order.

### Algorithm:


Start


Declare a string and read it from the user.


Sort the string in lexicographical order.


Use a function next_permutation() to generate the next permutation.


Print all permutations until no more exist.


End.



### Program:

~~~c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

// Function to swap two characters
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to reverse a string
void reverse(char *str, int l, int r) {
    while (l < r) {
        swap(&str[l], &str[r]);
        l++;
        r--;
    }
}

// Function to find next permutation
int next_permutation(char *str) {
    int i = strlen(str) - 2;
    while (i >= 0 && str[i] >= str[i + 1])
        i--;
    if (i < 0)
        return 0;
    int j = strlen(str) - 1;
    while (str[j] <= str[i])
        j--;
    swap(&str[i], &str[j]);
    reverse(str, i + 1, strlen(str) - 1);
    return 1;
}

int main() {
    char str[50];
    printf("Enter a string: ");
    scanf("%s", str);

    // Sort string initially
    for (int i = 0; i < strlen(str) - 1; i++)
        for (int j = i + 1; j < strlen(str); j++)
            if (str[i] > str[j])
                swap(&str[i], &str[j]);

    printf("Permutations in lexicographical order:\n");
    do {
        printf("%s\n", str);
    } while (next_permutation(str));

    return 0;
}
~~~

### Output:

~~~
Enter a string: ABC
Permutations in lexicographical order:
ABC
ACB
BAC
BCA
CAB
CBA
~~~

### Result:

Thus, the program is verified successfully. 

## EXP NO: 9 — C PROGRAM TO PRINT A PATTERN OF NUMBERS FROM 1 TO N

### Aim:

To write a C program to print a pattern of numbers from 1 to n.

### Algorithm:


Start


Declare integer variables n, i, j, min.


Read the value of n from the user.


Compute the length of the square matrix as len = n * 2 - 1.


Use nested loops to print the pattern.


The value at each cell = n - min(i, min(j, min(len - 1 - i, len - 1 - j))).


End.



### Program:

~~~c
#include <stdio.h>

int main() {
    int n;
    printf("Enter n: ");
    scanf("%d", &n);

    int len = n * 2 - 1;

    for (int i = 0; i < len; i++) {
        for (int j = 0; j < len; j++) {
            int min = i < j ? i : j;
            if (len - 1 - i < min)
                min = len - 1 - i;
            if (len - 1 - j < min)
                min = len - 1 - j;
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
~~~

### Output:

~~~
Enter n: 3
3 3 3 3 3
3 2 2 2 3
3 2 1 2 3
3 2 2 2 3
3 3 3 3 3
~~~

### Result:

Thus, the program is verified successfully. 

## EXP NO: 10 — C PROGRAM TO FIND THE SQUARE OF A NUMBER USING FUNCTION WITHOUT ARGUMENTS BUT WITH RETURN TYPE

### Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments but returns the square of the number.

### Algorithm:


Start


Define a function square() that takes no parameters but returns an integer.


Inside the function:


Ask the user to input a number.


Calculate and return its square.




In main(), call the function and print the result.


End.



### Program:

~~~c
#include <stdio.h>

int square();

int main() {
    int result;
    result = square();
    printf("Square of the number is: %d\n", result);
    return 0;
}

int square() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    return n * n;
}
~~~

### Output:

~~~
Enter a number: 5
Square of the number is: 25
~~~

### Result:

Thus, the program is verified successfully. 
