
Over this Fall, I have spent a decent amount of time parsing various namespaces.  Hopefully, this post will be helpful to anyone in my same position.  

### What exactly is a namespace?

<p>
It is ironic that, while namespace syntax is one of the first lines of code copied in a beginners C++ class, its function remains mysterious.  In my experience, I simply remembered to hard-wire my programs to always “include namespace std;.”  This changed a little as I progressed into slightly more structured programs, but for the most part, “include namespace std;” became a common practice.  
</p>

<p>
In freshman year, I remember some of the particularly vocal students inquiring about the need for the namespace call.  My instructor’s response, simply put, was that we could look into the scope resolution operator, but a functional understanding wouldn’t be needed now.  This notion of rolling over understanding carried on for the bulk of my instruction as a CS student.  Occasionally, I would run into an instance where scope resolution was needed, but this ‘trade in’ for a namespace call seemed mechanical, and frankly, confused me even more.
</p>

The archetypical example of the risk of namespace key word is shown below.  
```
#include <iostream>
using namespace std;
int main()
{
  cout<<"Hello World!!!"<<endl;
  return EXIT_SUCCESS;
}
```
Moreover the same code could be written as
```
#include <iostream>
//using namespace std;
int main()
{
  std::cout<<"Hello World!!!"<<std::endl;
  return EXIT_SUCCESS;
}
```
* note that in this hello world program, cout and endl are members of the standard namespace or (std). *

<p>
I don’t think it was my instructor’s fault because for all practical purposes, a mechanical understanding of namespace structure is definitely not required for introduction to programming students.  For myself, I simply just assumed its use was akin to a class.  And in a sense, from an organizational perspective, I wasn’t wrong.  Technically, name spaces and classes function much differently from each other in C+

See:
https://www.geeksforgeeks.org/difference-namespace-class/
</p>

<p>
In retrospect, I think the bulk of my confusion came from the idea of the “free function” concept in C++.  “Everything is an object” languages such as Java and C# are structurally void of this practice.   
</p>

<p>
On a top-level,  namespaces provide another step of organization for large programming projects.  A great analogy for this is given in Alex Allain’s Jumping Into C++, 
</p>


> A name space functions in the same way that a company division might function -- inside a name space you include all functions appropriate for fulfilling a certain goal.


<p>
As mentioned before, my software development internship has recently sparked a newfound point of confusion and interest in name space structure.  While I had a functional idea of their use, I believe that the frequency and abstraction in large, department level development set me off.  Through exposure and independent study, my understanding has definitely cleared up.    
</p>

### Other notes:

While tracing code, I was unfamiliar with the practice of nesting name spaces.  A comparison of nested vs non-nested namespaces is shown below.  

```
Using namespace _NameSpaceName
//Makes all content (classes/functions/variables) visible to the scope of the call
```

```
Using _NameSpaceName::NameSpaceName_Class
//Makes only the specific class of the namespace visible to the scope of the call
```





