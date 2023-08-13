#### The Importance of Scoping 

<p>
As I wrap up my task development, I have directing my focus towards testing and validation.
This software cycle step is primarily dedicated towards the writing of unit tests.
These tests are intended to test individual blocks of development for proper functionality.  Below I will describe a memorable dilemma from this week.  
</p>

<p>
While writing tests, I ran into an issue pertaining the incrementation of flagged errors.
Immediately I went back to my source code and inspected my modified syntax.
To no avail, I meticulously traced the passed variables to possibly find error source.
Eventually, I resorted to using a command-line debugger to trace all related variables. 
</p>

<p>
After a few days, I emailed my software architect to ask for his advice.
With an extra set of eyes, we ran though my code unable to find a source of error.
As a final resort, he suggested that I trace each unit test for expected clarity. 
</p>

 eureka !

<p>
In sum, I was so focused on the source code, I didn’t think to scan the tests themselves.
The error returned was due to the fact that I used a global “error count” variable.
The scope of this error type encompassed throughout my entire unit test class.
In order to reach the expected error count the variable must be reset over each individual unit test.
To combat this, I simply initialized the counter locally within the unit tests.  
</p>
