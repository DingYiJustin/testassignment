# Assignment2

Before doing this assignment, you should already know the following things:

- Operator ++, --
- Using for loop and while loop
- Using if and switch
- Array
- How to use cout

## Review Questions

(You should write the answers to the following questions in the same file)

1. Write down the output of the program

```c
int j = 0;
while (++j < 9) {
   cout << j++ << endl;
}
```

2. Write a loop that will output from 2 to the power of 1 to 2 to the power of 10. The output should look like: `2 4 8 16 32 64 128 256 512 1024`

3. Read the following code. Rewrite it without `break` and `continue`

```c
// you should run this program yourself first to understand it
int line = 0;
char ch;
// if there's any char data unread from the console, the loop will run, and each loop will read a character into ch from the console
// when character 'Q' is read, end the loop
while (cin.get(ch)) {
   if (ch == 'Q')
      break;
   if (ch != '\n')
      continue;
   line++;
}
```

## Programming Exercise

## Additional Exercise
### NO BONUS POINTS, just for fun :)

### The Rod Cutting Problem description  
Given a rod of length $n$ and prices $p_i$ for $i = 1, ..., 𝑛$, where $p_i$ is the price of a rod of length $i$. Find a way to cut the rod to maximize total revenue.  
For example, $n=4,p_n=\{2,5,6,11\}$. For the length of 4 rod, there are the following cutting methods:  
- 4 (11)
- 3+1 (8)
- 2+2 (10)
- 2+1+1 (9)
- 1+1+1+1 (8)  

So, for rod length of 4 the max revenue will be 11  

Another example, $n=4,p_n=\{3,6,7,11\}$. For the length of 4 rod, there are the following cutting methods:  
- 4 (11)
- 3+1 (10)
- 2+2 (12)
- 2+1+1 (12)
- 1+1+1+1 (12)  

So, for rod length of 4 the max revenue will be 12  

### How to Solve the Problem
We will use **dynamic programming** to solve the problem.  
Let $r_i$ be the maximum revenue obtainable from cutting a rod of length $i$. Our goal is finding $r_n$.  
For a rod of length $n$, assume the "first" cut length is $j$, which leaves a piece of length $n-j$. And the total value would be $p_j+r_{n-j}$. So, for $j$ from $1$ to $n$, the max value of $p_j+r_{n-j}$ would be the max revenue.  
Then, how to find $r_i$ for all $i$ in $\{0,1,...,n\}$? Since $r_n$ can be drived from $\{r_1,...,r_{n-1}\}$, $r_{n-1}$ can also be drived from $\{r_0,...,r_{n-2}\}$. And we already know $r_0=0,r_1=p_1$, then we can get $r_2,...,r_n$.  
If you need a more detailed explanation, please read [this document](./reference_comp3711_dp1.pdf) from COMP3711 **(pseudo code inside :o)**.

### Your Mission
Now you know how to solve the problem, please implement the code in [exer2_2.cpp](./exer2_2.cpp) such that the program will output the maximum revenue.

We have provided the skeleton code [exer2_2.cpp](./exer2_2.cpp), you only need to complete the missing part, input and output is already done.
For compiling and running the code, using the following commend lines:

```bash
# compile
g++ -o exer_run2_2 exer2_2.cpp
# run
./exer_run2_2
```

If you want to know more about compiling with g++, click [here](https://courses.cs.washington.edu/courses/cse373/99au/unix/g++.html)

## DO NOT FORGET TO COMMIT AND PUSH YOU CODE :)
