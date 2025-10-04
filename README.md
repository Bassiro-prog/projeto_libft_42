
# 📚 Libft – 42 Project  

O **Libft** é uma biblioteca em C que implementa funções básicas da biblioteca padrão do C (como as do `<string.h>`, `<stdlib.h>` e mais), além de algumas funções extras para listas encadeadas (parte bônus).  

🎯 **Objetivo?** Recriar do zero ferramentas essenciais para entender como tudo funciona por baixo dos panos. Nada de copiar-colar: é tudo handmade, respeitando as regras rígidas da 42 (sem `printf`, sem leaks de memória, e com um Makefile sem relink).  

Essa lib é o alicerce para projetos futuros da 42, como **get_next_line**, **So Long**, **Pipex** e muitos outros.  
Se você é aluno da 42, sabe a dor... e a glória!  

📌 Por que *"libft"*? Porque é a *libft* – a **biblioteca livre (e livre de bugs... mais ou menos 😅)**.  

---

## ⚙️ Estrutura  

A lib é dividida em duas partes:  

- **Parte 1**: funções obrigatórias (*Libc-like*)  
- **Parte 2**: funções adicionais  
- **Bônus**: listas encadeadas (`t_list`)  

---

## 🔨 Funções  

### Parte 1 – Funções da libc reimplementadas  
- `ft_strlen`, `ft_strlcpy`, `ft_strlcat`, `ft_strncmp`, `ft_strdup`,  
- `ft_strchr`, `ft_strrchr`, `ft_memset`, `ft_memcpy`, `ft_memmove`,  
- `ft_memchr`, `ft_memcmp`, `ft_bzero`, `ft_calloc`, `ft_atoi`,  
- `ft_isalpha`, `ft_isdigit`, `ft_isalnum`, `ft_isascii`, `ft_isprint`,  
- `ft_toupper`, `ft_tolower`.  

### Parte 2 – Funções adicionais  
- `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`,  
- `ft_itoa`, `ft_strmapi`, `ft_striteri`,  
- `ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`.  

### Bônus – Listas encadeadas (`t_list`)  
- `ft_lstnew`, `ft_lstadd_front`, `ft_lstadd_back`, `ft_lstsize`, `ft_lstlast`,  
- `ft_lstdelone`, `ft_lstclear`, `ft_lstiter`, `ft_lstmap`.  

---
## 📦 Instalação

Clone o repositório e compile a biblioteca:

```bash
git clone https://github.com/Bassiro-prog/libft.git
cd libft
make       # gera o arquivo libft.a
make clean # remove objetos
make fclean # remove tudo (incluindo libft.a)
make re     # recompila do zero
E nunca esqueça do norminette 😈

💡 Exemplos de Uso
<details> <summary>🔹 Manipulando Strings</summary>
c
Copiar código
#include "libft.h"
#include <stdio.h>

int main(void) {
    char *str = ft_strdup("Hello, 42!");
    char *trimmed = ft_strtrim(str, " !");
    printf("Original: %s\n", str);      // "Hello, 42!"
    printf("Trimmed: %s\n", trimmed);   // "Hello, 42"
    
    char **split = ft_split("ola,mundo,42", ',');
    printf("Split[0]: %s\n", split[0]); // "ola"
    // Lembre-se de dar free(split) e free(str)!
    return (0);
}
</details> <details> <summary>🔹 Listas Encadeadas</summary>
c
Copiar código
#include "libft.h"
#include <stdio.h>

int main(void) {
    t_list *head = ft_lstnew(ft_strdup("Primeiro"));
    ft_lstadd_back(&head, ft_lstnew(ft_strdup("Segundo")));
    ft_lstadd_front(&head, ft_lstnew(ft_strdup("Zero")));
    
    t_list *temp = head;
    while (temp) {
        printf("%s -> ", (char *)temp->content);
        temp = temp->next;
    }
    // Output: Zero -> Primeiro -> Segundo ->
    
    ft_lstclear(&head, free);  // Libere a memória!
    return (0);
}
</details> ```
📈 Status
<img width="598" height="204" alt="image" src="https://github.com/user-attachments/assets/d434854e-1fa7-4384-a57e-d4f03013c19d" />

🚧 Futuro: otimizações e integração em outros projetos

🤝 Contribuições

Quer contribuir? Abra um PR ou sugira testes via issues.
Mas lembre: siga a norma da 42 (25 linhas por função, sem variáveis globais, etc.).

🙏 Agradecimentos

À 42, por me torturar (quer dizer, ensinar).

Aos peers que revisaram e debugaram comigo.

👤 Feito com ❤️ por Bassiro Nanque – 42 School
⭐ Se curtiu, deixa uma estrela no repo!
