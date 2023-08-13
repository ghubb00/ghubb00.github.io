For comparisons, I will reference the following code snippet (C++ syntax) to better illustrate Prolog/Smalltalk syntax.  

```
using namespace std;
int sumFunc(int);

int main() {
    int n;
    std::cin>>n;  //user defines max number to sum
    int sum = sumFunc(n);
    cout<<sum<<endl;
    return 0;
    }
/*
 Adds the current increment (starting at 0)
 to the sum of increments before it
 ex:
 n = 0; sum = 0
 n = 1; sum = 0
 n = 2; sum = 0 + 1
 n = 3; sum = 1 + 2
 n = 4; sum = 3 + 3
 n = 5; sum = 6 + 4
 
	visually “triangular number sequence - 1”:
 n = 2      *
 n = 3     ***
 n = 4    ******
 n = 5  **********
 
 This pattern can be described as a triangular number sequence
 */

int sumFunc(int n)
{
int sum = 0;
for (int i = 0; i<n; i++)
{
    sum = sum + i;
}
return sum;
}
```
**Prolog**

Prolog is a declarative language.  The given code is written in an imperative manner such that the language describes how to compute a solution.  To implement the given code in Prolog, the program must consist of rules and logical relationships that ascribe meaning to the application.  When a program is prompted an input, the run time system searches though the declared rules (by logical deduction) to produce an output.  

I have rewritten the function of the given program below.
```
sumprint(N) :-
    write('sum is '),
    sum(N,Sum), write(Sum), nl.


sum(N,Sum) :-    
 sum(N,0,0,Sum).
 sum(0,_,Sum,Sum). 

 sum(C,X,T,Sum) :-   
   C > 0 ,         
   T1 is T+X ,     
   X1 is X+1 ,     
   C1 is C-1 ,     
   sum(C1,X1,T1,Sum).    
```

Aside from obvious syntax differences, the major difference between the given code and my Prolog rendition is due to the declarative nature of prolog.  Since prolog is a declarative language, two major changes must be made.

Firstly, there are no functions in prolog.  Because of this, the functions of main() and sumFunc(int n) must be written as general relations.  

Secondly, prolog does not have iteration.  This means that the operation of sumFunc(int n) must be modified completely to remove the for loop.  To compensate for this, the for loop iteration can be rewritten using recursion in prolog.  In my prolog rendition, “tail-recursion” is used to in place of iteration.  

Like the given C++ code, input/output is possible in prolog.  Additionally, despite the fact that prolog lacks function types, the my prolog code organizes major operations in the same manner that the C++ code does.  In this sense, there is a relation for input/out much like main() and there is a relation for calculating the sum much like sumFunc(int n).



**SmallTalk**

SmallTalk is an example of a “pure” object oriented language.  In comparison to hybrid systems like C++ or Java, primitive types do not exist and all data (including integers, characters, arrays, classes, etc.) are stored as objects.  
Building on this, unlike Java and C++, smallTalk is dynamically typed meaning you do not need to know the type of your object before you use it.

In C++ and Java there is a notion of public and private methods (functions).  In Smalltalk every method is accessible to any object.  Additionally, all methods in Smalltalk return values meaning that there is no explicit concept of “void” return.  

My rendition of the given code in Smalltalk shown below:

```
| n count sum|

n := FillInTheBlank request: 'Prompt Me'. 
count := 0.
sum := 0.

[count < n] whileTrue: [
	sum := count +sum.
	count := count + 1. 
	].

Transcript show: sum; cr.
```

Clearly, this code is much more readable than the given prolog code.  Like C++ and Java, it is possible to loop/iterate.  Although Smalltalk does not have a construct for for loops, it is possible to rewrite the given code in a while loop.  This function could also be written recursively like the prolog example. 

Just like C++ and Java, user input is possible.  As state before, Smalltalk recognizes all information as an object and in that regard is considered “typeless”.  Notably, this difference clearly seen in the discrepancy between the manner C++ code prompts for data vs the manner Smalltalk code’s prompts for data.  C++’s stream will look for an integer input and will not pass the data otherwise.  With the given Smalltalk code it is possible to input a non-integer value on prompt but will fail as the compiler will not know what to do with the type mismatch on count < n.  This issue can be mitigated by adding “n := n asInteger.” after prompting data in the rewritten code.  

Other notable differences between the Smalltalk code and the C++ code can be seen in the syntax.  I personally feel as though Smalltalk is easier to read with the operations being quite explicit (ie: “cout<<” vs “FillInTheBlank request” for user input).  

Interestingly, variable declaration in Smalltalk is done, as seen in the sample code, in the following format: “| n count sum|”.  I found this rather unique compared to my programing experience and is nothing like C++/Java as it is typeless and lacks (,) separation between identifiers.  

The code on the Squeak IDE with input 6 is shown below
 
