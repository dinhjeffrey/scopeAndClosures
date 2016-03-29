#[Function Scope Exercises](id:xcredit)
[Back to Home](https://github.com/bgando/JS102)

#####It is your mission to go through the function.js file and change all occurances of `'???'` so that each test passes.

###Let's get started...

Explore the files in the **ExtraCredit** folder.
 
Run the file in a browser. This document shows one passed test and a series of failing tests.

The **functions.js** folder holds all the failing tests that are being displayed in **SpecRunner.html**. You will be editing this file and using the **SpecRunner.html** to check your progress on making these tests pass. This is just a javascript file so you can use console.log to help debug and inspect these functions.

A test block starts with an `it` function. The `it` function takes two arguments. The first one is a statement describing the rule addressed by the test. The second is a function that will throw an error if the assertion made using the `expect` function does not hold. For example, the assertion `expect(ACTUAL).to.equal('inner');` throws an error if `ACTUAL` is does not contain the value `'inner'`. You can almost read it like plain English.

####Failing Test Example
```js
it('has access to its own local scope variables', function () {
    var fn = function () {
      var name = 'inner';
      ACTUAL = name;
    }; 
    fn();
    expect(ACTUAL).to.equal('???'); 
    //change '???' to what ACTUAL evaluates to.
});
```

####Passing Test Example
```js
it('has access to its own local scope variables', function () {
    var fn = function () {
      var name = 'inner';
      ACTUAL = name;
    }; 
    fn();
    expect(ACTUAL).to.equal('inner'); 
    //changed '???' to 'inner' 
    //(because we assigned ACTUAL, a global variable to name inside fn)
});
```
### Don't forget..
To read all code to try to understand how the whole testing process works. Welcome to programming :)

---
