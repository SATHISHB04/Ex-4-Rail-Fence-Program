# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

Enter the secret message and number of rails.


Create a matrix with the specified number of rails.


Place the message characters in a zigzag pattern.


Change the direction at the top and bottom rails.


Read the characters row by row.


Display the resulting text as the encrypted message.
# PROGRAM
```#include <stdio.h>
#include <string.h>

int main()
{
    char msg[100];
    int rail, i, j, row = 0, dir = 1;

    printf("Enter message: ");
    fgets(msg, 100, stdin);

    printf("Enter number of rails: ");
    scanf("%d", &rail);

    msg[strcspn(msg, "\n")] = '\0';

    char a[rail][100];

    for (i = 0; i < rail; i++)
        for (j = 0; j < 100; j++)
            a[i][j] = ' ';

    for (i = 0; msg[i] != '\0'; i++)
    {
        a[row][i] = msg[i];

        if (row == 0)
            dir = 1;
        if (row == rail - 1)
            dir = -1;

        row += dir;
    }

    printf("Encrypted Message: ");

    for (i = 0; i < rail; i++)
        for (j = 0; msg[j] != '\0'; j++)
            if (a[i][j] != ' ')
                printf("%c", a[i][j]);

    return 0;
}
```
# OUTPUT
<img width="1657" height="782" alt="image" src="https://github.com/user-attachments/assets/61bc98ea-cc49-4e30-87c8-48544d65f514" />

# RESULT
The implementation of rail fence transposition technique using c program is successful.
