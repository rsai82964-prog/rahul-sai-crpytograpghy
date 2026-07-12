Program 1:
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100];
    int key, i;

    printf("Enter the plaintext: ");
    fgets(text, sizeof(text), stdin);

    printf("Enter the key (1-25): ");
    scanf("%d", &key);

    for(i = 0; text[i] != '\0'; i++)
    {
        if(text[i] >= 'A' && text[i] <= 'Z')
        {
            text[i] = (text[i] - 'A' + key) % 26 + 'A';
        }
        else if(text[i] >= 'a' && text[i] <= 'z')
        {
            text[i] = (text[i] - 'a' + key) % 26 + 'a';
        }
    }

    printf("Ciphertext: %s", text);

    return 0;
}
}

Program 2:
#include <stdio.h>
#include <string.h>

int main()
{
    char text[100];
    char cipher[] = "QWERTYUIOPASDFGHJKLZXCVBNM";
    int i;

    printf("Enter the plaintext: ");
    fgets(text, sizeof(text), stdin);

    for(i = 0; text[i] != '\0'; i++)
    {
        if(text[i] >= 'A' && text[i] <= 'Z')
        {
            text[i] = cipher[text[i] - 'A'];
        }
        else if(text[i] >= 'a' && text[i] <= 'z')
        {
            text[i] = cipher[text[i] - 'a'] + 32;
        }
    }

    printf("Ciphertext: %s", text);

    return 0;
}
