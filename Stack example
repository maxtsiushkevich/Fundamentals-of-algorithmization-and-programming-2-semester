//пример работы со стеком
#include <stdlib.h>
#include <stdio.h>
#include <locale.h>
#define SIZE 50
struct linkedList
{
    char data[SIZE];
    struct linkedList *next;
} *stack=NULL, *stackElement;
void push(struct linkedList **);
void pop(struct linkedList **);
void see(struct linkedList *);

int main()
{
    //struct linkedList *stack = NULL;
    char choice; // (англ.) пункт меню
    setlocale(LC_ALL, "Russian");
    while (1)
    {
        puts("Вид операции:");
        puts(" 1 − создать/добавить");
        puts(" 2 − удалить");
        puts(" 3 − просмотреть");
        puts(" 0 − окончить");
        fflush(stdin);
        choice = getchar();
        switch (choice)
        {
            case '1':
                push(&stack);
                break;
            case '2':
                if (stack)
                    pop(&stack);
                else
                    puts("Стек пуст");
                break;
            case '3':
                see(stack);
                break;
            case '0':
                return 0;
            default:
                printf("Ошибка, повторите ввод!\n");
        }
    }
}

void pop(struct linkedList **stack) // Функция удаления последнего элемента стека
{
    //struct linkedList *stackElement = *stack;
    *stack = (*stack)->next;
    free(stackElement);
    puts("Последний элемент стека удален\n");
}

void push(struct linkedList **stack) // Функция cоздания/добавления в стек
{
    //struct linkedList *stackElement = *stack;
    do
    { // выделяем память под один элемент стэка
        if (!(*stack = (struct linkedList *)calloc(1, sizeof(struct linkedList))))
        {
            puts("Нет свободной памяти!");
            return;
        }
        puts("Введите данные:");
        fflush(stdin);
        gets((*stack)->data); // ввод строки в поле data
        (*stack)->next = stackElement; //новый элемент стека указывает на предыдущий
        stackElement = *stack; // элементу присваиваем новый элемент стека
        puts("Продолжить (y/n)?");
        fflush(stdin);
    } while (getchar() == 'y');
}

void see(struct linkedList *stack) // Функция просмотра элементов стека
{
    //struct linkedList *stackElement;
    stackElement = stack;
    if (!stack)
    {
        puts("Стек пуст");
        return;
    }
    puts("Элементы стека:");
    do
    {
        printf("%s\n", stackElement->data);
        stackElement = stackElement->next;
    } while (stackElement);
puts("Вывод стека закончен\n");
}

