NAME : PRIYADHARSHINI G
REG NO : 212224230209

## EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
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
```
#include <stdio.h>

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);

    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0;
}
```




Output:

<img width="227" height="72" alt="image" src="https://github.com/user-attachments/assets/a8e2f2c7-61a6-4eee-bb77-570a6deb6503" />


Result:
Thus, the program is verified successfully
 
## EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
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
```
#include <stdio.h>

int main() {
    char a[50];
    int i, d, c;

    printf("Enter a number string: ");
    scanf("%s", a);

    for (d = 0; d <= 3; d++) {
        c = 0;
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] - '0' == d)
                c++;
        }
        printf("%d ", c);
    }

    return 0;
}

```

Output:


<img width="407" height="85" alt="image" src="https://github.com/user-attachments/assets/2e0c88ca-9e3d-4b91-8ae8-ca5bd9fb9dbd" />


Result:
Thus, the program is verified successfully

## EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
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
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

void permute(char *str, int l, int r) {
    int i;
    if (l == r)
        printf("%s\n", str);
    else {
        for (i = l; i <= r; i++) {
            swap((str + l), (str + i));
            permute(str, l + 1, r);
            swap((str + l), (str + i));
        }
    }
}

int main() {
    char str[50];
    printf("Enter a string: ");
    scanf("%s", str);

    int n = strlen(str);
    printf("Permutations in lexicographical order:\n");

    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (str[i] > str[j]) {
                char temp = str[i];
                str[i] = str[j];
                str[j] = temp;
            }
        }
    }

    permute(str, 0, n - 1);
    return 0;
}
```


Output:


<img width="470" height="229" alt="image" src="https://github.com/user-attachments/assets/bd862e35-37f6-4fd2-a397-8b703acc9be7" />



Result:
Thus, the program is verified successfully
 
## EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
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
```
#include <stdio.h>

int main() {
    int n, i, j, min, len;

    printf("Enter n: ");
    scanf("%d", &n);

    len = n * 2 - 1;

    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            int top = i;
            int left = j;
            int right = (len - 1) - j;
            int bottom = (len - 1) - i;
            min = top < left ? top : left;
            if (right < min) min = right;
            if (bottom < min) min = bottom;
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```


Output:


<img width="178" height="190" alt="image" src="https://github.com/user-attachments/assets/c6c78c44-d1e0-4fa0-a411-a283e795f81d" />




Result:
Thus, the program is verified successfully

## EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

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
```
#include <stdio.h>

int square() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    return n * n;
}

int main() {
    int result;
    result = square();
    printf("Square of the number is: %d\n", result);
    return 0;
}
```

Output:

<img width="377" height="96" alt="image" src="https://github.com/user-attachments/assets/c290756e-53db-4e00-9ce1-511c05722c3b" />




Result:
Thus, the program is verified successfully





