# Project Description
* This repo was created for me to learn testing JavaScript.
* I am using a FreeCodeCamp Tutorial: [https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/](/https://www.freecodecamp.org/news/how-to-test-javascript-code-with-jest/)

## Project Commentary
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
