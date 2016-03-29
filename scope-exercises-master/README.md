#[Function Scope Exercises](id:xcredit)
[Back to Home](https://github.com/bgando/JS102)

#####It is your mission to go through the function.js file and change all occurances of `'???'` so that each test passes.

###Let's get started...

Explore the files in the **ExtraCredit** folder.
 
Run the file in a browser. This document shows one passing test and a series of failing tests.

The **functions.js** file holds all the failing tests that are displayed by launching **SpecRunner.html**. You will be editing **functions.js** and checking the output of **SpecRunner.html** to check your progress. This is just a javascript file so you can use console.log to help debug and inspect these functions.

A test block starts with an `it` function. The `it` function takes two arguments. The first is a string describing the rule addressed by the test. The second is a function that should throw an error if the assertion made using `expect` does not hold. For example, the assertion `expect(ACTUAL === 'inner').to.be.true;` throws an error if `ACTUAL === 'inner'` evaluates to `false`. You can almost read it like plain English.

####Failing Test Example
```js
it('has access to variables in its own local scope', function () {
    var fn = function () {
      var name = 'inner';
      ACTUAL = name;
    }; 
    fn();
    expect(ACTUAL === '???').to.be.true; 
    //change '???' to what ACTUAL evaluates to.
});
```

####Passing Test Example
```js
it('has access to variables in its own local scope', function () {
    var fn = function () {
      var name = 'inner';
      ACTUAL = name;
    }; 
    fn();
    expect(ACTUAL === 'inner').to.be.true; 
    //changed '???' to 'inner' 
    //(because we assigned ACTUAL, a global variable to name inside fn)
});
```
### Don't forget..
To read all code to try to understand how the whole testing process works. Welcome to programming :)

---
