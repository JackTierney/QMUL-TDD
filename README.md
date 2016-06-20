# QMUL-TDD

## An introduction to TDD

If you want to write code in JavaScript, or any language, you know what you want to do. You know that to accomplish that goal, you will need to write functions.
How do you know if those functions are correct? (For our purposes, correct means the function behaves as expected).

The answer is to write another function which tests the first function. We will refer to the second function as a "test function". The first function is the one that is being tested - it is "under test".

For example, suppose you have a function called qmul:

```javascript
var qmul = function () {};
```

To test this function, you would write another function called testQmul:

```js
var testQmul = function () {};
```

In this example, testQmul is the test function, and qmul is the function under test.

>>>>>>>>>> Here https://repl.it/C4Hu/1



## How does the test function work?

The test function will call the function under test. In order to do that we will need to pass the function under test as an argument to the test function.

For example, in order for testQmul to test the qmul function, testQmul needs to accept an argument, e.g. Arg:

```js
var testQmul = function(arg) {};
//Then, when we call testQmul, we simply pass qmul as a parameter:

testQmul(qmul);
```


## How does the test function work? Part 2

We said that the test function must call the function under test. Let's do that.

We'll assign the result to a variable called "actual" which we will use later.

>>>>>>>>>>>> Here https://repl.it/C4Hy/3


## Make the test fail...

So far our test function doesn't do anything useful.

What do we want it to do? It would be useful if our test function ran the function under test and compared the result to some expected value.

If the results are equal, the test passes. Otherwise the test fails.

###So, we need:

an ```expected``` value containing the value we expect to see when we call the function
an ```actual``` value containing the result of actually calling the function
We'll use a function to compare these two values.

Declare a function called areEqual that accepts two arguments, expected and actual. This function should return true if the two values are equal, false otherwise.

Next, declare a new variable inside testQmul called expected and assign it a value of 1. Then, also inside testQmul, return the result of calling the areEqual function, passing expected and actual as parameters.

>>>>>>>>>>>>> Here https://repl.it/C4IE/1


# ...then update foo so that the test passes

In the last exercise we updated our test to expect a value of 1. The actual value returned by qmul() is "undefined". When we passed these values to "areEqual" the result was false.

So, now all we have to do is update qmul to make the test pass. How do we do that?

Instructions
Update the foo function so that it returns a value that will make the test pass.

>>>>>>>>>>>> Here https://repl.it/C4IK


#Making qmul useful.


The qmul function is not very useful, but the example in this section illustrates the point: we have a function - qmul, and we have a test function - testQmul. The test function tells us without a doubt that the function under test behaves as expected. This is extremely powerful.

Also note that in these exercises, the *LAST* thing we did was update qmul. We wrote our test first, then we wrote our qmul function. This is known as "Test Driven Development". It is a philosophy that has been used extensively in manufacturing and in software development.

We will use Test Driven Development to make a more interesting function that behaves as expected.

## Review of Section 1

When we write functions, it's useful to know whether our functions are correct.
Test Driven Development is a process where we write a test function to test another function. We go in cycles:

* We write a new test
* We confirm that the test fails
* We update the function under test just enough so that the new test passes
* We repeat these steps over and over until we are satisfied that our function under test is correct.

To begin with, let's review how to write a test:

"Write a test called *testQmul* with an argument of *arg* where the ```expected``` value is *3* when the parameter passed is *5*".

# Read that instruction sentence carefully. Such a test would look like this:

```js
var testQmul(arg) {
    var actual = arg(5);
    var expected = 3;
    return areEqual(expected, actual);
};
```

Read the instruction sentence again. Note the bold text: "testQmul", "arg", "3", "5".
Each of these values appears in the function definition above. For the remainder of this lesson, when you write a test, it should look pretty much the same, except that the bold text should be replaced with different values. Which values? That should be evident in the instruction.

In this example, testQmul accepts a function arg as an argument. It stores the value 3 in the variable "expected". It then calls arg, passing 5 as a parameter, and stores the result in "actual". It then compares actual to expected using a function called areEqual and returns the result, which will either be true or false.

Now it's your turn.

# Instructions
Write the areEqual function. It should be the same as the areEqual function you wrote in the last section.

Next, write an empty function called "tree" that accepts one argument called "myVal".

Then, write a test called testTree with an argument of func where the expected value is "tree" when the parameter passed is true.

Finally, call testTree passing in tree as a parameter.

>>>>>>>> Here https://repl.it/C4IW




# Factorial Begins

Great stuff, We're now going to write a function that returns the factorial of a number.


Factorial is a mathematical operation. It applies only to positive integers. The factorial of a number n is the product of that number with every other positive integer less than n. So the factorial of 1 is 1. The factorial of 2 is 2 x 1 = 2. The factorial of 3 is 3 x 2 x 1 = 6. And so on. You are probably doing a Maths heavy subject so I am sure you have come across factorial!



However before we begin, let's think about some tests we need to write.

Factorial of 1 should return 1
Factorial of 2 should return 2
Factorial of 3 should return 6
Calling the factorial of any value other than a positive integer should return ```undefined```
Factorials can be huge numbers. For simplicity, and more coding practise lets make sure that calling the factorial of 21 or higher returns undefined

Instructions
Write a test called "testFactorial_1" where the expected value is 1 when the parameter passed is 1.

Then, call testFactorial_1 passing in factorial as a parameter.

I've included the areEqual function and the factorial function for you.

Let's get started.

>>>>>>>> Here https://repl.it/C4I1


# Great, now make the test pass.....

Nice work! We can add the other tests now.
Here's the list of tests we wrote earlier:

* DONE: Factorial of 1 should return 1  
Factorial of 2 should return 2
Factorial of 3 should return 6
Calling the factorial of any value other than a positive integer should return undefined
Factorials can be huge numbers. For simplicity, lets make sure that calling the factorial of 21 or higher returns undefined
Let's move on.

Instructions
Write a test called "testFactorial_2" where the expected value is 2 when the parameter passed is 2.

Then, call testFactorial_2 passing in factorial as a parameter.

>>>>>>>> Here https://repl.it/C4I6


## now make the test pass...... again.

Once again, we have a test in place. Now, we need to make the new test pass.

Instructions
Update factorial to return 2 when the argument is 2. 

* Remember, you must do this in such a way that the previous test - testFactorial_1 - still passes!!!
* 

>>>>>> Here  https://repl.it/C4Ic


Factorial: The Dark Function Rises
Excellent!

Look at the version of factorial to the right. Notice it is just returning the value of n. Is that how yours looked? If not, that's ok. Just be aware of the simple way I made the test pass. I didn't try to solve any other problem, I just made the test pass. Keep that in mind as we go forward.

Let's keep adding tests.
Here's a review of the list of tests we need:

DONE: Factorial of 1 should return 1
DONE: Factorial of 2 should return 2

Factorial of 3 should return 6

Calling the factorial of any value other than a positive integer should return undefined

Factorials can be huge numbers. For simplicity, lets make sure that calling the factorial of 21 or higher returns undefined

Things are going to start getting a little trickier. It's time to write testFactorial_3.

Instructions
Write a test called "testFactorial_3" where the expected value is 6 when the parameter passed is 3.

Then, call testFactorial_3 passing in factorial as a parameter.


>>>>>>> Here https://repl.it/C4Ie


### now make the test pass... didn't we already do this?

Our third test is in place. Making it pass is a tiny bit harder than the previous test. Look for the **simplest** possible way to make the test pass. Take your time. Only make it pass the test.

Instructions
Update factorial to return 6 when the argument is 3. Remember, you must do this in such a way that the previous tests still pass.

##Nearly done!

Once again, look at my version of factorial:

>>>>>>>> Here https://repl.it/C4Ii

Again, I made **just enough** changes to make my tests pass.

It seems our factorial function is really seeming to work well now, right?

What?

You don't think it's done yet? Ok, smarty pants. Let's test that theory. Add another test. I'm sure it will pass...

Instructions
Write a test called "testFactorial_7" where the parameter passed is 7. Use a calculator to figure out what the expected value is.

Then, call testFactorial_7 passing in factorial as a parameter. It should pass right??? 

>>>>>> Here https://repl.it/C4Il



## Oops
The testFactorial7 test doesn't pass after all. Making testFactorial7 pass is likely to involve a general solution for all legal values of n. Give it a try. See if you can incorporate a for loop from earlier.


>>>>>>> Here https://repl.it/C4Ir



# Nearly done now 



Don't worry if you didn't come up with this general solution on your own. Ideally, you would keep inventing tests (i.e. for other values of n) until the general solution became clear.

We still have two more tests to do. Here's our updated list of tests:

DONE: Factorial of 1 should return 1
DONE: Factorial of 2 should return 2
DONE: Factorial of 3 should return 6
DONE: Factorial of 7 should return 5040

Calling the factorial of any value other than a positive integer should return undefined

Factorials can be huge numbers. For simplicity, lets make sure that calling the factorial of 21 or higher returns undefined

Let's finish this list off.

Instructions
Write a test called "testFactorial_21" where the expected value is undefined when the parameter passed is 21 or more.

Then, call testFactorial_21 passing in factorial as a parameter.


>>>>>>> Here https://repl.it/C4Iv



#...make the test pass
Our testFactorial_21 is in place. Making it pass is fairly straightforward.


# Last one.
We're nearly there. We just need to check for invalid values of n.

Instructions
Write a test called "testFactorial_string" where the expected value is undefined when the parameter passed is "foo".

Then, call testFactorial_string passing in factorial as a parameter.

BEFORE YOU CLICK Save & Submit Code, look at factorial. Can you see any issue with calling it, passing a string as a parameter? What do you think might happen? DON'T FIX IT (or you'll get an Oops), just think about what might happen.

>>>>>>>>> Here https://repl.it/C4Iv/1

#Before we continue
It was mentioned in the feedback that I overlooked a crucial test:

Factorial of 0 is 1

Instructions
Write a test called "testFactorial_0" where the expected value is 1 when the parameter passed is 0.

Then, call testFactorial_0 passing in factorial as a parameter.

look at the factorial method. What do you think will happen when you pass 0 to this function?, just think about what might happen.

>>>>>>>>>> Here https://repl.it/C4Il

#Make testFactorial_0 pass

The testing process is iterative.

You will find that, having written your tests and made them pass, after some time, other tests come to mind. You can add them as you think of them. testFactorial_0 is such an example.



Another important case
Here's another crucial test I overlooked:

Factorial of (less than zero) is undefined

Instructions
Write a test called "testFactorial_lessThanZero" where the expected value is undefined when the parameter passed is -1.

>>>>>>>> Here https://repl.it/C4KJ

Then, call testFactorial_lessThanZero passing in factorial as a parameter. Once again, look at the factorial method. What do you think will happen when you pass a value less than 0 to this function? DON'T TRY!!!!! just have a think.


# Now finally update that.

# Summary
Excellent work! Really! This lesson has been long and arduous but you stuck with it.

What the factorial sections hopefully illustrated was an iterative approach to programming - you write some test and confirm that it fails, then you make it pass. Then you write some test and confirm that it fails, then make it pass... and so on.

Review the code one last time. Feel free to play around with it. There are some things to be aware of:

* We did not cover at least one important test: what if n is a decimal value? I leave this as an exercise for you to work through on your own.

* We did a lot of repetition in our tests. Perhaps we could have found a way to re-use some of that code.
Normally in test driven development, a test should inform you when the test fails, and only then. That way, you can tell at a glance whether or not your tests pass, and if not which tests failed. In a future lesson we'll improve on the model of our test functions and the areEqual function.

* One of the things testing affords us is the ability to update our code with confidence. Since we have tests in place, we know immediately if an update breaks the code.
