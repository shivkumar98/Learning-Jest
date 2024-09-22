# 🧠 Learning Jest 🧠
* This repo was created for me to learn testing JavaScript.
* I am using a FreeCodeCamp Tutorial: [https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/](/https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/)

## 🟥 Setting Up Project and Jest 🟥
* I download Git onto to my computer so I can access the terminal
* I open Git bash in the root of this project, an executed the following:
```sh
npm init -y
```
* This created a `package.json` file
<details>

```json
{
  "name": "learning-jest",
  "version": "1.0.0",
  "description": "* This repo was created for me to learn testing JavaScript.\r * I am using a FreeCodeCamp Tutorial: [https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/](/https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/)",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```
</details>

* I runn the following command to add the Jest dependency into this project:
```sh
npm install --save-dev jest
```
* This creates a `node_modules` folder to the root of this project
* I can see Jest has been added to `package.json`:
```json
{
   "name": "learning-jest",
   "version": "1.0.0",
   "description": "* This repo was created for me to learn testing JavaScript.\r * I am using a FreeCodeCamp Tutorial: [https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/](/https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/)",
   "main": "index.js",
   "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1"
   },
   "keywords": [],
   "author": "",
   "license": "ISC",
   "devDependencies": {
      "jest": "^29.7.0"
   }
}
```
* I change the `test` key of `scripts` to `jest`:
```json:
"scripts": {
   "jest": "echo \"Error: no test specified\" && exit 1"
}
```

## 🟥 Basic Concepts in Jest 🟥
* I start with creating a simple unit test, I create `sum.js` and `sum.test.js` files.
* The `sum.js` file is defined as:
```js
function sum(a,b) {
   return a + b;
}
module.exports = sum;
```
* The last line is to allow other JS files to access the `sum()` function
* In the `sum.test.js` file, I import the sum module using `require`:
```js
const sum = require('./sum');
```
* I create my first test by calling the `test()` function:
```js
test('adds 1 and 2 to equal 3', () => {
   expect(sum(1,2)).toBe(3);
})
```
* I now need to run the test, so I execute `npm test` but I get the following error:
```sh
npm test
npm error Missing script: "test"
npm error
npm error Did you mean this?
npm error   npm run jest # run the "jest" package script
npm error
npm error To see a list of scripts, run:
npm error   npm run
npm error A complete log of this run can be found in: C:\Users\shiv_\AppData\Local\npm-cache\_logs\2024-09-22T13_52_25_097Z-debug-0.log
```
* I fix this by updating the `package.json` to:
```json
"scripts": {
   "test": "jest"
},
```
* Now when I execute the test:
```
npm test

> learning-jest@1.0.0 test
> jest

PASS ./sum.test.js
  √ adds 1 and 2 to equal 3 (1 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        0.356 s
Ran all test suites.
```


## 🟥 Matchers in Jest 🟥
* `.toBe()` is one example of a matcher, there are various other matchers!
* `.toBe()` is for JavaScript PRIMITIVES (booleans, strings, numbers), not for objects like arrays:
```js
test('two plus two is four', ()=> {
   expect(2+2).toBe([1,2,3]); // FAIL :(
})
```
* The above fails with the following error:
```
expect(received).toBe(expected) // Object.is equality

Expected: [1, 2, 3]
Received: 4
```

* We have the `toEqual()` matcher for objects:
```js
test('objects need to use toEqual()', ()=> {
   const object = {one:1, two:2};
   expect(object).toEqual({one:1, two: 2}); // PASS
})
```
* We can also evaluate if a value is falsy using the `toBeFalsy()` matcher:
```js
test('null is falsy', ()=> {
   const nullVar = null;
   expect(nullVar).toBeFalsy(); // PASS
})
```
* If we tried to use `isEqual(false)` or `toBe(false)`, the test will fail⚠️⚠️⚠️
* We also have `toBeTruthy()`:
```js
const one = 1;
expect(one).toBeTruthy(); // PASS
```
* We also have a `toThrow()` matcher:
```js
const n = () => {
   throw new Error()
}
expect(n).toThrow(); // PASS
```