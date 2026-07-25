# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM

```
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100];
    char rail[10][100];
    int depth, len;
    int i, j;
    int row = 0, dir = 1;
    printf("Enter the plaintext: ");
    scanf("%s", text);
    printf("Enter the number of depth: ");
    scanf("%d", &depth);
    len = strlen(text);
    for(i = 0; i < depth; i++)
    {
        for(j = 0; j < len; j++)
        {
            rail[i][j] = '*';
        }
    }
    for(i = 0; i < len; i++)
    {
        rail[row][i] = text[i];

        if(row == 0)
            dir = 1;
        else if(row == depth - 1)
            dir = -1;

        row = row + dir;
    }
    printf("\nRail Matrix:\n");
    for(i = 0; i < depth; i++)
    {
        for(j = 0; j < len; j++)
        {
            printf("%c ", rail[i][j]);
        }
        printf("\n");
    }

    printf("\nCiphertext: ");
    for(i = 0; i < depth; i++)
    {
        for(j = 0; j < len; j++)
        {
            if(rail[i][j] != '*')
                printf("%c", rail[i][j]);
        }
    }

    printf("\n");

    return 0;
}

```
# OUTPUT

<img width="1906" height="1022" alt="image" src="https://github.com/user-attachments/assets/f6c5427a-d892-40a6-8a10-5fc76b5e9525" />

# RESULT
Thus, the Rail Fence Cipher using the specified depth was implemented successfully using the C programming language, and the corresponding ciphertext was obtained.
