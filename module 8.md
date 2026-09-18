EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

#include <stdio.h>

int main()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n)
    {
        case 1:
            printf("one");
            break;
        case 2:
            printf("two");
            break;
        case 3:
            printf("three");
            break;
        case 4:
            printf("four");
            break;
        case 5:
            printf("five");
            break;
        case 6:
            printf("six");
            break;
        case 7:
            printf("seven");
            break;
        case 8:
            printf("eight");
            break;
        case 9:
            printf("nine");
            break;
        default:
            printf("Greater than 9");
    }

    return 0;
}



Output:


<img width="1810" height="715" alt="image" src="https://github.com/user-attachments/assets/ccd11c5a-0da5-485e-b580-bd19567d7071" />


Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:
#include <stdio.h>

int main()
{
    char a[50];
    int c, i, j, h;

    scanf("%[^\n]", a);

    h = 0;

    while (h < 4)
    {
        c = 0;

        for (i = 0; a[i] != '\0'; i++)
        {
            if (a[i] == '0' + h)
            {
                c++;
            }
        }

        printf("%d ", c);
        h++;
    }

    return 0;
}






Output:






Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void swap(char *a, char *b)
{
    char temp = *a;
    *a = *b;
    *b = temp;
}

void permute(char *s, int l, int r)
{
    int i;

    if (l == r)
    {
        printf("%s\n", s);
        return;
    }

    for (i = l; i <= r; i++)
    {
        swap(&s[l], &s[i]);
        permute(s, l + 1, r);
        swap(&s[l], &s[i]);
    }
}

int compare(const void *a, const void *b)
{
    return strcmp(*(const char **)a, *(const char **)b);
}

int main()
{
    char **s;
    int n, i;

    printf("Enter number of strings: ");
    scanf("%d", &n);

    s = (char **)malloc(n * sizeof(char *));

    if (s == NULL)
    {
        printf("Memory allocation failed.\n");
        return 1;
    }

    for (i = 0; i < n; i++)
    {
        s[i] = (char *)malloc(50 * sizeof(char));

        if (s[i] == NULL)
        {
            printf("Memory allocation failed.\n");
            return 1;
        }

        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }

    printf("\nPermutations:\n");

    for (i = 0; i < n; i++)
    {
        printf("\nPermutations of %s:\n", s[i]);
        permute(s[i], 0, strlen(s[i]) - 1);
    }

    for (i = 0; i < n; i++)
    {
        free(s[i]);
    }

    free(s);

    return 0;
}




Output:

<img width="1795" height="761" alt="image" src="https://github.com/user-attachments/assets/6448661f-7aec-4d9f-9d05-26344153944b" />


Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

#include <stdio.h>

int main()
{
    int n, i, j, min, len;

    printf("Enter n: ");
    scanf("%d", &n);

    len = n * 2 - 1;

    for (i = 0; i < len; i++)
    {
        for (j = 0; j < len; j++)
        {
            min = i;

            if (j < min)
                min = j;

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




Output:


<img width="1878" height="816" alt="image" src="https://github.com/user-attachments/assets/b27584d5-4d61-4249-98ff-456df10b62b1" />



Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

#include <stdio.h>

int square()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    return n * n;
}

int main()
{
    int result;

    result = square();

    printf("Square = %d\n", result);

    return 0;
}




Output:


<img width="1907" height="776" alt="image" src="https://github.com/user-attachments/assets/01cf9964-7dfa-4f1e-9786-a5c6f4e6ecec" />


Result:
Thus, the program is verified successfully



























