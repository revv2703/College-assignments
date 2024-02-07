**Loops**

1. How many times CppBuzz.com is printed?

```cpp
#include<iostream>
int main()
{
    int i=0;
lbl:
    std::cout<<"CppBuzz.com";
    i++;
    if(i<5)
    {
	goto lbl;
    }

    return 0;

}
```

    - Infinite times

2. Find the output of below program.

```cpp
#include<iostream>

int main()
{
for(int i=1;i<=2;i++)
{
for(int j=i;j<=2;j++)
{
std::cout<<i<<”@”;
}
}
}
```

    -C) 1@1@2@

3. How many times will Quiz be printed in the above program?

```cpp
#include <stdio.h>
int main()
{
    int i = 1024;
    for (; i; i >>= 1)
        printf("Quiz");
    return 0;
}
```

    -A) 10

4. Q4. WAP using while loop. Input: read two non-negative numbers x and y
   //Output: write the product x and y // Constraint: do not use the \* operator

   - The code will be as follows:

```cpp
#include <iostream>
using namespace std;

int main() {
    int x, y, prod = 0;

    cout << "Enter two non-negative integers x and y: ";
    cin >> x >> y;

    while (y > 0) {
        prod += x;
        y--;
    }

    cout << "Product of x and y is: " << prod << endl;

    return 0;
}
```

5. What is the output of the program below?

```cpp
#include<iostream>
using namespace std;

int main()
{
int n = 3;
while (n >= 0)
{
cout << n * n << endl;
--n;
}
cout << n << endl;
while (n < 4)
   cout << ++n << endl;
cout << n << endl;

return 0;
}
```

    - The output will be as follows:

```
9
4
1
0
-1
0
1
2
3
4
4
```

6. The loop shown below has been written by an inexperienced C/C++ programmer. The behavior of the loop is not correctly represented by the formatting.
```cpp
   int n = 10;
   while (n > 0) n /= 2;
   cout << n * n << endl;
```
   
a. What is the output of the loop as it is written?
    - 0
b. Correct the syntax of the loop so that the logic of the corrected loop corresponds to the formatting of the original loop. What is the output of the corrected loop?
    - The code will be as follows:
```cpp
    int n = 10;
    while (n > 0){ 
        n /= 2;
        cout << n * n << endl; 
    }
```
c. Correct the formatting of the (original) loop so that the new format reflects the logical behavior of the original loop.
    - The code will be as follows:
```cpp
    int n = 10;
    while (n > 0)
        n /= 2;
    cout << n * n << endl;
```

7. Answer the questions below concerning the following fragment of code.
```cpp
int n; cout << "Enter an integer: "; 
cin >> n; 
if (n < 10) cout << "less than 10" << endl; 
else if (n > 5)
    cout << "greater than 5" << endl; 
else cout << "not interesting" << endl
```

a. less than 10
b. greater than 5
c. greater than 5
d. 6 to 9(inclusive)

8. Rewrite the following code fragment so that it uses a "do...while..." loop to accomplish the same task. 
```cpp
int n; 
cout << "Enter a non-negative integer: "; 
cin >> n; 
while (n < 0) 
{ 
    cout << "The integer you entered is negative." << endl;
    cout << "Enter a non-negative integer: ";
    cin >> n; 
}
```

    - The code will be as follows:
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    do {
        cout << "Enter a non-negative integer: ";
        cin >> n;
        if (n < 0)
            cout << "The integer you entered is negative." << endl;
    } while (n < 0);
    return 0;
}
```

9. What is the output when the following code fragment is executed? 
```cpp
#include<iostream>
using namespace std;
int main()
{
int n; 
float x = 3.8;
n = int(x); 
cout << "n = " << n << endl; 
return 0;
}
```

    - n = 3

10. The following loop is an endless loop: when executed it will never terminate. What modification can be made in the code to produce the desired output? 
```cpp
cout << "Here's a list of the ASCII values of all the upper" << " case letters.\n";
char letter = 'A';
while (letter <= 'Z') 
    cout << letter << " " << int(letter) << endl; 
```

    - The code will be as follows:
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Here's a list of the ASCII values of all the upper case letters.\n";
    char letter = 'A';
    while (letter <= 'Z') {
        cout << letter << " " << int(letter) << endl;
        letter++;
    }
    return 0;
}
```

11. Write a program using while loop. Take two two integer arguments, call them "first" and "last", and returns as its value the sum of all the integers between first and last inclusive. 

    - The code will be as follows:
```cpp
#include <iostream>
using namespace std;

int main() {
    int first, last;
    cout << "Enter first and last integers: ";
    cin >> first >> last;
    int sum = 0;
    while (first <= last) {
        sum += first;
        first++;
    }
    cout << "Sum of integers between first and last inclusive: " << sum << endl;
    return 0;
}
```

12. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main() {
    int n ;
    for (n = 5; n >0; n--) 
    {
        cout << n;
        if (n == 3) 
        break;
    }
    return 0;
}
```

    - 543

13. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main() {
    int n = 15;
    for (; ;) 
    cout << n;
    return 0;
}
```

    - C) infinite times of printing value of n

14. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
int main() {
    int i ;
    for (i = 0; i < 10; i++);
    {
        cout << i;
    }
    return 0;
}
```

    - B) 10

**Functions**

1. Which of the following is the default return value of functions in C++?
- A) int

2. What happens to a function defined inside a class without any complex operations (like looping, a large number of lines, etc)?
- C) It becomes an inline function of the class

3. In which of the following cases inline functions may not work?
- D) i, iii, iv

4. If an argument from the parameter list of a function is defined constant then
- B) It cannot be modified inside the function

5. What will be the output of the following C++ code?
```cpp
#include<iostream>
using namespace std;
 
int fun(int x = 0, int y = 0, int z)
{  return (x + y + z); }
 
int main()
{
   cout << fun(10);
   return 0;
}
```

- C) Error    (You need defualt values for all parameters(maybe))

6. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
void square (int *x, int *y)
{
	*x = (*x) * --(*y);
}
int main ( )
{
	int number = 30;
	square(&number, &number);
	cout << number;
	return 0;
}

```

- A) 870

7. How many can max number of arguments present in function in the C++ compiler?
- D) 127

8. What will be the output of the following C++ code?
```cpp
#include <iostream>
using namespace std;
void fun(int x, int y){
    x = 20;
    y = 10;
}
int main() 
{
   int x = 10;
    fun (x, x);
    cout << x;
    return 0;
}

```

- A) 10

9. Identify the correct extension of the user-defined header file in C++.
- C) .h

10. C++ uses which approach?
- B) Top-down

11. When can an inline function be expanded?
- B) Compile Time

12. What is the output of the following program?
```cpp
#include <iostream>
using namespace std;
int main()
{
enum color_type {red, orange, yellow, green, blue, violet};
color_type shirt, pants;
shirt = red;
pants = blue;
cout << shirt << " " << pants << endl;
return 0;
}
```
    - 0 4

13. Write a function named "sum_from_to" that takes two integer arguments, call them "first" and "last", and returns as its value the sum of all the integers between first and last inclusive. 

```cpp
#include <iostream>
using namespace std;

int sum_from_to(int first, int last) {
    int sum = 0;
    for (int i = first; i <= last; ++i) {
        sum += i;
    }
    return sum;
}
```

14. Write a function named "enough" that takes one integer argument, call it "goal" and returns as its value the smallest positive integer n for which 1+2+3+. . . +n is at least equal to goal. 

```cpp
#include <iostream>
using namespace std;

int enough(int goal) {
    int sum = 0, n = 1;
    while (sum < goal) {
        sum += n;
        ++n;
    }
    return n - 1;
}
```

15. Write a program that contains a class Sample with three function in it fun1( ), fun2( ) and fun3( ). All 3 functions receive an int and a float. fun1( ) receives them by value, fun2( ) by address and fun3( ) by reference. All of them increment the int and float by 1. 
Which function would be able to change the original value of int and float?
- `fun3()` will be able to change the original value of `int` and `float`.

Can these functions be defined as overloaded functions?
- Yes, these functions can be defined as overloaded functions.
