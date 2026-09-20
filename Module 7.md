## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

### Aim:

To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

### Algorithm:

1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
### Program:

~~~c
#include <stdio.h>

struct eligible {
    char n[50];
    int age;
};

int main() {
    struct eligible e[100];
    int n, i;

    printf("Enter number of persons: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("\nEnter name: ");
        scanf("%s", e[i].n);
        printf("Enter age: ");
        scanf("%d", &e[i].age);
    }

    printf("\n--- Vaccine Eligibility Check ---\n");
    for (i = 0; i < n; i++) {
        printf("\nName: %s", e[i].n);
        printf("\nAge: %d", e[i].age);
        if (e[i].age <= 6)
            printf("\nVaccine Eligibility: No\n");
        else
            printf("\nVaccine Eligibility: Yes\n");
    }

    return 0;
}
~~~


### Output:

~~~
Enter number of persons: 3

Enter name: Arjun
Enter age: 5

Enter name: Praveen
Enter age: 12

Enter name: Sneha
Enter age: 8

--- Vaccine Eligibility Check ---

Name: Arjun
Age: 5
Vaccine Eligibility: No

Name: Praveen
Age: 12
Vaccine Eligibility: Yes

Name: Sneha
Age: 8
Vaccine Eligibility: Yes
~~~


### Result:

Thus, the program is verified successfully. 


## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION

### Aim:

To write a C program for passing structure as function and returning a structure from a function

### Algorithm:

1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
### Program:

~~~c
#include <stdio.h>

// Structure definition
struct numbers {
    int a, b, sum;
};

// Function declaration
struct numbers add(struct numbers n);

int main() {
    struct numbers n1, result;

    printf("Enter two numbers: ");
    scanf("%d %d", &n1.a, &n1.b);

    // Function call and storing returned structure
    result = add(n1);

    printf("\nSum of %d and %d is: %d\n", result.a, result.b, result.sum);

    return 0;
}

// Function to add two numbers using structure
struct numbers add(struct numbers n) {
    struct numbers temp;
    temp.a = n.a;
    temp.b = n.b;
    temp.sum = n.a + n.b;
    return temp;
}
~~~




Output:

~~~
Enter two numbers: 10 25

Sum of 10 and 25 is: 35
~~~




Result:
Thus, the program is verified successfully


 
## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

### Aim:

To write a C program to read a file name from user

### Algorithm:

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
 
### Program:

~~~c
#include <stdio.h>

int main() {
    FILE *p;
    char name[50];

    printf("Enter the file name to create: ");
    scanf("%s", name);

    p = fopen(name, "w");  // open file in write mode

    if (p == NULL) {
        printf("Error! Unable to create file.\n");
        return 1;
    }

    printf("File '%s' created and opened successfully.\n", name);

    fclose(p);
    printf("File '%s' closed successfully.\n", name);

    return 0;
}
~~~




### Output:

~~~
Enter the file name to create: sample.txt
File 'sample.txt' created and opened successfully.
File 'sample.txt' closed successfully.
~~~











### Result:

Thus, the program is verified successfully
 


## EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE

### Aim:

To write a C program to read, a file and insert text in that file

### Algorithm:

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
 
### Program:

~~~c
#include <stdio.h>

int main() {
    FILE *p;
    char name[50], text[100];
    int num, i;

    printf("Enter the file name to create: ");
    scanf("%s", name);

    printf("Enter the number of lines to write: ");
    scanf("%d", &num);

    p = fopen(name, "w");  // open file in write mode

    if (p == NULL) {
        printf("Error! Unable to create or open the file.\n");
        return 1;
    }

    printf("\nFile '%s' opened successfully.\n", name);
    printf("Enter %d lines of text:\n", num);

    // Clear input buffer
    getchar();

    for (i = 0; i < num; i++) {
        printf("Line %d: ", i + 1);
        fgets(text, sizeof(text), stdin);
        fputs(text, p);
    }

    fclose(p);
    printf("\nData has been written to '%s' successfully.\n", name);

    return 0;
}
~~~




### Output:

~~~
Enter the file name to create: notes.txt
Enter the number of lines to write: 3

File 'notes.txt' opened successfully.
Enter 3 lines of text:
Line 1: Vaccine eligibility program completed.
Line 2: Structure experiment tested.
Line 3: File handling successful.

Data has been written to 'notes.txt' successfully.
~~~






### Result:

Thus, the program is verified successfully



## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

### Aim:

The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

### Algorithm:

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

### Program:

~~~c
#include <stdio.h>
#include <stdlib.h>

struct student {
    char name[50];
    int marks;
};

int main() {
    struct student *s;
    int n, i;

    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    // Dynamically allocate memory
    s = (struct student*)malloc(n * sizeof(struct student));

    if (s == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Input student details
    for (i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf("%s", s[i].name);
        printf("Enter marks for %s: ", s[i].name);
        scanf("%d", &s[i].marks);
    }

    // Display student details
    printf("\n--- Student Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: %s\n", i + 1, s[i].name);
        printf("Marks: %d\n\n", s[i].marks);
    }

    // Free allocated memory
    free(s);

    return 0;
}
~~~



### Output:

~~~
Enter the number of subjects: 3

Enter name of subject 1: Maths
Enter marks for Maths: 95

Enter name of subject 2: Science
Enter marks for Science: 88

Enter name of subject 3: English
Enter marks for English: 92

--- Student Details ---
Subject 1: Maths
Marks: 95

Subject 2: Science
Marks: 88

Subject 3: English
Marks: 92
~~~






### Result:

Thus, the program is verified successfully
