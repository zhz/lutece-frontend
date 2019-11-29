## What compilers does the online judge use?

|Language|Compiler|Version|Commands|
|-|-|-|-|
|C++|GNU G++|7.3.0|g++ -w -O2 -DONLINE_JUDGE -fmax-errors=15 --std=gnu++17 {sourcefile}.cpp -lm -o {sourcefile}.bin|
|C|GNU GCC|7.3.0|gcc -w -O2 -DONLINE_JUDGE -fmax-errors=15 --std=c11 {sourcefile}.c -lm -o {sourcefile}.bin|
|Python|Python|3.6.5|python3 {sourcefile}.py|
|Java|OpenJDK|10|javac {sourcefile}.java|
|Go|Go|1.10.2|go run {sourcefile}.go|
|Ruby|Ruby|2.5.1|ruby {sourcefile}.rb|
|Rust|Rust|1.26.1|rustc -O {sourcefile}.rs -o {sourcefile}.bin|

## Show me the code of A+B Problem.
C:
```c
/* This also shows how to use 64-bit integer. */
#include <stdio.h>
int main()
{
    long long a,b;
    while(scanf("%lld%lld",&a,&b)!=EOF) printf("%lld\n",a+b);
    return 0;
}
```
C++:
```c++
#include <iostream>
using namespace std;
int main()
{
    int a,b;
    while(cin>>a>>b) cout<<a+b<<endl;
    return 0;
}
```
Java:
```java
import java.util.Scanner;
public class Main {
    public static void main(String[] args)
    {
        Scanner in=new Scanner(System.in);
        while (in.hasNextInt())
        {
            int a=in.nextInt();
            int b=in.nextInt();
            System.out.println(a+b);
        }
    }
}
```
Python:
```python
s=input().split()
print(int(s[0])+int(s[1]))
```


## What does the result in status page mean?
|Result|Explanation|
|-|-|
|Pending|You solution will be judged soon.|
|Preparing|Your solution is on the way.|
|Compile Error|Failed to compile your source code. check the compiler's output at the page bottom.|
|Running|Your program is running. Please wait for result.|
|Runtime Error|Your program terminated abnormally. Possible reasons are: segment fault, divided by zero or exited with code other than 0.|
|Accepted|Congratulations. Your solution is correct.|
|Wrong Answer|Your program's output doesn't match judger's answer.|
|Time Limit Exceeded|   The CPU time your program used has exceeded limit. Java has a triple time limit.|
|Memory Limit Exceeded| The memory your program actually used has exceeded limit.|
|Output Limit Exceeded| Your program has produced too much output. The limit of output is 16mb.|
|Judge Error|Got error while checking your program , this mostly meaning the Lutece service failed.|

It is known that Memory Limit Exceeded and Runtime Error would be judged as Restricted Function sometimes.
Judge Error,Oops, something has gone wrong with the judger. Please report this to administrator.