1. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main() {
    int i=5;
    int j=i++;
    cout << "j= " << j << "  i= "<<i<<endl;
    return 0;
}
```
    - B) j=5 i=6

2. Which of the following gives the memory address of the first element in array?
    - D) array

3. The operator used for dereferencing or indirection is ____
    - A) *

4. What is the meaning of the following declaration?
```cpp
int(*p[5])();
```
    - B) p is array of pointer to function

5. What will be the output of the following C++ code?
```cpp
#include <stdio.h>
#include<iostream>
using namespace std;
int main()
{
    int a = 5, b = 10, c = 15;
    int arr[3] = {&a, &b, &c};
    cout << *arr[*arr[1] - 8];
    return 0;
}
```
    - D) compile time error

6. What will happen in the following C++ code snippet?
```CPP
int a = 100, b = 200;
int *p = &a, *q = &b;
p = q;
```
    - B) p now points to b

7. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main()
{
    char arr[20];
    int i;
    for(i = 0; i < 10; i++)
        *(arr + i) = 65 + i;
    *(arr + i) = '\0';
    cout << arr;
    return(0);
}
```
    - A) ABCDEFGHIJ

8. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main()
{
    char *ptr;
    char Str[] = "abcdefg";
    ptr = Str;
    ptr += 5;
    cout << ptr;
    return 0;
}
```
    - A) fg

9. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main()
{
    int arr[] = {4, 5, 6, 7};
    int *p = (arr + 1);
    cout << arr;
    return 0;
}
```
    - C) address of arr

10. The pointer can point to any variable that is not declared with which of these?
    - C) Both A & B

11. A void pointer cannot point to which of these?
    - C) Both A & B

12. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main()
{
    int arr[] = {4, 5, 6, 7};
    int *p = (arr + 1);
    cout << *p;
    return 0;
}
```
    - B) 5

13. Which of the following statement is correct about the program given below?
```cpp
int main()
{
    int a[2][4] = {1, 2, 3, 4, 5, 6, 7, 8};
    cout << *(a[1] + 2) << *(*(a + 1) + 2) << 2[1[a]];
    return 0;
}  
```
    - B) 7 7 7

14. Which of the following is true about the following program
```cpp
#include <iostream>
using namespace std;
int main()
{
   int i;
   char *lfc[] = {"C", "C++", "Java", "VBA"};
   char *(*ptr)[4] = &lfc;
   cout << ++(*ptr)[2];
   return 0;
}  
```
    -  A) ava

15. What would be printed from the following C++ program? 
```cpp 
#include <stdio.h>
void fun(int x)
{
    x = 30;
}
int main()
{
    int y = 20;
    fun(y);
    printf("%d", y);
    return 0;
}
```
    - B) 20 

16. What would be printed from the following C++ program? 
```cpp
#include <iostream>
using namespace std;
int main()
{
    int x[5] = { 1, 2, 3, 4, 5 };
    
    int* p = x;
    int i;
    for (i = 0; i < 2; i++) {
        int temp = *(p + i);
        *(p + i) = *(p + 4 - i);
        *(p + 4 - i) = temp;
    }
    
    for (i = 0; i < 5; i++)
        cout << x[i] << " ";
    return 0;
}
```
    - A) 5 4 3 2 1

17. What will be the output of the following program?
```cpp
#include <iostream> 
using namespace std;   
int main() 
{ 
    int a = 32, *ptr = &a; 
    char ch = 'A', &cho = ch; 
    cho += a; 
    *ptr += ch; 
    cout << a << ", " << ch << endl; 
    return 0; 
} 
```
    - C) 129, a

18. What will be the output of the following program?
```CPP
#include <iostream> 
using namespace std; 
int main() 
{ 
    int arr[] = { 4, 5, 6, 7 }; 
    int* p = (arr + 1);
    cout << *arr + 10; 
    return 0; 
} 
```
    - C) 14

19. What does array decay refer to in C++?
    - B) Loss of array type information and conversion to a pointer

20. What is a pointer to an array in C++?
    - A) A variable that points to the first element of an array

21. How do you pass an array to a function in C++?
    - B) By passing the array name

22. What is the relationship between arrays and pointers in C++?
    - C) Arrays can be treated as pointers

23. How can you dynamically allocate an array in C++?
    - C) By declaring the array with a variable size

24. What is the correct way to deallocate a dynamically allocated array in C++?
    - A) delete[]

25. What will be the output of the following C++ code?
```cpp
#include <stdio.h>
#include <iostream>
using namespace std;
int main()
{
    int array[] = {10, 20, 30};
    cout << -2[array];
    return 0;
}
```
    - B) -30