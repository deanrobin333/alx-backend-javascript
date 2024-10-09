# Project
## **0x04. Typescript**
---
## Table of Contents
- [Author Details](#author-details)
- [Project Description](#project-description)
- [Tasks](#tasks)
	- [0. Creating an interface for a student](#0)
	- [1. Let's build a Teacher interface](#1)
	- [2. Extending the Teacher class](#2)
	- [3. Printing teachers](#3)
	- [4. Writing a class](#4)
	- [5. Advanced types Part 1](#5)
	- [6. Creating functions specific to employees](#6)
	- [7. String literal types](#7)
	- [8. Ambient Namespaces](#8)
	- [9. Namespace & Declaration merging](#9)
	- [10. Update task_4/js/main.ts](#10)
	- [11. Brand convention & Nominal typing](#11)
---
## Author Details
- *Dean Robin Otsyeno - deanrobin777@gmail.com*

## Project Description


## Tasks
#### 0
###### [Table of Contents](#table-of-contents)
**0. Creating an interface for a student**

- Copy the following configuration files (provided above) into the `task_0` directory: `package.json`, `.eslintrc.js`, `tsconfig.json`, `webpack.config.js`

- Write your code in the `main.ts` file:


   - Write an interface named Student that accepts the following elements: `firstName(string)`, `lastName(string)`, `age(number)`, and `location(string)`
   - Create two students, and create an array named `studentsList` containing the two variables
   - Using Vanilla Javascript, render a table and for each elements in the array, append a new row to the table
   - Each row should contain the first name of the student and the location


- Requirements:


   - When running, Webpack should return `No type errors found`.
   - Every variable should use TypeScript when possible.



<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_0/js/main.ts`](./task_0/js/main.ts)
    - File: [`task_0/package.json`](./task_0/package.json)
    - File: [`task_0/.eslintrc.js`](./task_0/.eslintrc.js)
    - File: [`task_0/tsconfig.json`](./task_0/tsconfig.json)
    - File: [`task_0/webpack.config.js`](./task_0/webpack.config.js)
---
#### 1
###### [Table of Contents](#table-of-contents)
**1. Let's build a Teacher interface**

- Create a directory `task_1` and copy these configuration files into this folder: `package.json`, `tsconfig.json`, `webpack.config.js`


   - `firstName(string)` and `lastName(string)`. These two attributes should only be modifiable when a Teacher is first initialized
   - `fullTimeEmployee(boolean)` this attribute should always be defined
   - `yearsOfExperience(number)` this attribute is optional
   - `location(string)` this attribute should always be defined
   - Add the possibility to add any attribute to the Object like `contract(boolean)` without specifying the name of the attribute


- Example:

```
const teacher3: Teacher = {

  firstName: 'John',
  fullTimeEmployee: false,
  lastName: 'Doe',
  location: 'London',
  contract: false,
};

console.log(teacher3);

// should print
// Object
// contract: false
// firstName: "John"
// fullTimeEmployee: false
// lastName: "Doe"
// location: "London"
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_1/js/main.ts`](./task_1/js/main.ts)
    - File: [`task_1/webpack.config.js`](./task_1/webpack.config.js)
    - File: [`task_1/tsconfig.json`](./task_1/tsconfig.json)
    - File: [`task_1/package.json`](./task_1/package.json)
---
#### 2
###### [Table of Contents](#table-of-contents)
**2. Extending the Teacher class**

- Write an interface named `Directors` that extends `Teacher`. It requires an attribute named `numberOfReports(number)`

- Example:

```
const director1: Directors = {

  firstName: 'John',
  lastName: 'Doe',
  location: 'London',
  fullTimeEmployee: true,
  numberOfReports: 17,
};
console.log(director1);

// should print
// Object
// firstName: "John"
// fullTimeEmployee: true
// lastName: "Doe"
// location: "London"
// numberOfReports: 17
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_1/js/main.ts`](./task_1/js/main.ts)
---
#### 3
###### [Table of Contents](#table-of-contents)
**3. Printing teachers**

- Write a function `printTeacher`:


   - It accepts two arguments `firstName` and `lastName`
   - It returns the first letter of the firstName and the full lastName
   - Example: `printTeacher("John", "Doe") -> J. Doe`


- Write an interface for the function named `printTeacherFunction`.


<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_1/js/main.ts`](./task_1/js/main.ts)
---
#### 4
###### [Table of Contents](#table-of-contents)
**4. Writing a class**

- Write a Class named `StudentClass`:


   - The constructor accepts `firstName(string)` and `lastName(string)` arguments
   - The class has a method named `workOnHomework` that return the string `Currently working`
   - The class has a method named `displayName`. It returns the firstName of the student
   - The constructor of the class should be described through an Interface
   - The class should be described through an Interface


- Requirements:


   - You can reuse the Webpack configuration from the previous exercise to compile the code.
   - When running `npm run build`, no TypeScript error should be displayed.
   - Every variable should use TypeScript when possible.



<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_1/js/main.ts`](./task_1/js/main.ts)
---
#### 5
###### [Table of Contents](#table-of-contents)
**5. Advanced types Part 1**

- Create the `DirectorInterface` interface with the 3 expected methods:


   - `workFromHome()` returning a string
   - `getCoffeeBreak()` returning a string
   - `workDirectorTasks()` returning a string


- Create the `TeacherInterface` interface with the 3 expected methods:


   - `workFromHome()` returning a string
   - `getCoffeeBreak()` returning a string
   - `workTeacherTasks()` returning a string


- Create a class `Director` that will implement `DirectorInterface`


   - `workFromHome` should return the string `Working from home`
   - `getToWork` should return the string `Getting a coffee break`
   - `workDirectorTasks` should return the string `Getting to director tasks`


- Create a class `Teacher` that will implement `TeacherInterface`


   - `workFromHome` should return the string `Cannot work from home`
   - `getCoffeeBreak` should return the string `Cannot have a break`
   - `workTeacherTasks` should return the string `Getting to work`


- Create a function `createEmployee` with the following requirements:


   - It can return either a `Director` or a `Teacher` instance
   - It accepts 1 arguments:


     - `salary`(either number or string)

   - if `salary` is a number and less than 500 - It should return a new `Teacher`. Otherwise it should return a `Director`


- Expected result:

```
console.log(createEmployee(200));

Teacher
console.log(createEmployee(1000));
Director
console.log(createEmployee('$500'));
Director
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_2/js/main.ts`](./task_2/js/main.ts)
    - File: [`task_2/webpack.config.js`](./task_2/webpack.config.js)
    - File: [`task_2/tsconfig.json`](./task_2/tsconfig.json)
    - File: [`task_2/package.json`](./task_2/package.json)
---
#### 6
###### [Table of Contents](#table-of-contents)
**6. Creating functions specific to employees**

- Write a function `isDirector`:


   - it accepts `employee` as an argument
   - it will be used as a type predicate and if the employee is a director


- Write a function `executeWork`:


   - it accepts `employee` as an argument
   - if the employee is a Director, it will call `workDirectorTasks`
   - if the employee is a Teacher, it will call `workTeacherTasks`


- Expected result:

```
executeWork(createEmployee(200));

Getting to work
executeWork(createEmployee(1000));
Getting to director tasks
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_2/js/main.ts`](./task_2/js/main.ts)
---
#### 7
###### [Table of Contents](#table-of-contents)
**7. String literal types**

- Write a String literal type named `Subjects` allowing a variable to have the value `Math` or `History` only.
Write a function named teachClass:


   - it takes `todayClass` as an argument
   - it will return the string `Teaching Math` if `todayClass` is `Math`
   - it will return the string `Teaching History` if `todayClass` is `History`


- Expected result:

```
teachClass('Math');

Teaching Math
teachClass('History');
Teaching History
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_2/js/main.ts`](./task_2/js/main.ts)
---
#### 8
###### [Table of Contents](#table-of-contents)
**8. Ambient Namespaces**

- Create a directory called `task_3` and copy these configuration files into it: `package.json`, `webpack.config.js`, `tsconfig.json`.

- The first part of will require that you build an `interface` and a `type`. Inside a file named `interface.ts`:


   - Create a type `RowID` and set it equal to `number`
   - Create an interface `RowElement` that contains these 3 fields:


     - `firstName`: `string`
     - `lastName`: `string`
     - `age?`: `number`



- You are building the next part of the application architecture. The goal is to save the entities to a database.
Because of time constraints, you can’t write a connector to the database, and you decided to download a library called crud.js. Copy this file into the task_3/js directory.

- Here it is

- Write an ambient file within `task_3/js`, named `crud.d.ts` containing the type declarations for each crud function. At the top of the file import `RowID` and `RowElement` from `interface.ts`.
- In `main.ts`
- Create an object called `row` with the type `RowElement` with the fields set to these values:
- Create a `const` variable named `newRowID` with the type `RowID` and assign the value the `insertRow`  command.
- Next, create a `const` variable named `updatedRow` with the type `RowElement` and update `row` with an age field set to `23`
- Finally, call the `updateRow` and `deleteRow` commands.
- Expected result:
- Requirements:
```
export function insertRow(row) {

  console.log('Insert row', row);
  return Math.floor(Math.random() * Math.floor(1000));
}

export function deleteRow(rowId) {
  console.log('Delete row id', rowId);
  return;
}

export function updateRow(rowId, row) {
  console.log(`Update row ${rowId}`, row);

  return rowId;
}
const obj = {firstName: "Guillaume", lastName: "Salva"};

CRUD.insertRow(obj)
// Insert row {firstName: "Guillaume", lastName: "Salva"}

const updatedRow: RowElement = { firstName: "Guillaume", lastName: "Salva", age: 23 };
CRUD.updateRow(newRowID, updatedRow);
// Update row 125 {firstName: "Guillaume", lastName: "Salva", age: 23}

CRUD.deleteRow(125);
// Delete row id 125
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_3/js/main.ts`](./task_3/js/main.ts)
    - File: [`task_3/js/interface.ts`](./task_3/js/interface.ts)
    - File: [`task_3/js/crud.d.ts`](./task_3/js/crud.d.ts)
---
#### 9
###### [Table of Contents](#table-of-contents)
**9. Namespace & Declaration merging**

- Create a new directory `task_4` and copy the above `tsconfig.json` and put this `package.json` in there

- In `task_4/js/subjects`:
```
{

  "name": "task_4",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "webpack",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@typescript-eslint/eslint-plugin": "^2.4.0",
    "@typescript-eslint/parser": "^2.4.0",
    "clean-webpack-plugin": "^3.0.0",
    "fork-ts-checker-webpack-plugin": "^1.5.1",
    "html-webpack-plugin": "^3.2.0",
    "ts-loader": "^6.2.0",
    "typescript": "^3.6.4",
    "webpack": "^4.41.2",
    "webpack-cli": "^3.3.9",
    "webpack-dev-server": "^3.8.2"
  }
}
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_4/package.json`](./task_4/package.json)
    - File: [`task_4/tsconfig.json`](./task_4/tsconfig.json)
    - File: [`task_4/js/subjects/Cpp.ts`](./task_4/js/subjects/Cpp.ts)
    - File: [`task_4/js/subjects/Java.ts`](./task_4/js/subjects/Java.ts)
    - File: [`task_4/js/subjects/React.ts`](./task_4/js/subjects/React.ts)
    - File: [`task_4/js/subjects/Subject.ts`](./task_4/js/subjects/Subject.ts)
    - File: [`task_4/js/subjects/Teacher.ts`](./task_4/js/subjects/Teacher.ts)
---
#### 10
###### [Table of Contents](#table-of-contents)
**10. Update task_4/js/main.ts**


   - create and export a constant `cpp` for Cpp Subjects
   - create and export a constant `java` for Java Subjects
   - create and export a constant `react` for React Subjects
   - create and export one Teacher object `cTeacher` with `experienceTeachingC = 10`
   - for Cpp subject, log to the console `C++`, set `cTeacher` as the teacher, call the two methods `getRequirements` and `getAvailableTeacher` and print the strings they return
   - for Java subject, log to the console `Java`, set `cTeacher` as the teacher, call the two methods `getRequirements` and `getAvailableTeacher`, and print the strings they return
   - for React subject, log to the console `React`, set `cTeacher` as the teacher, call the two methods `getRequirements` and `getAvailableTeacher`, and print the strings they return


```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_4/js/main.ts`](./task_4/js/main.ts)
---
#### 11
###### [Table of Contents](#table-of-contents)
**11. Brand convention & Nominal typing**

- Create a directory `task_5` and copy these configuration files into the root of `task_5`: `package.json`, `tsconfig.json`, `webpack.config.js`

- Create two interfaces `MajorCredits` and `MinorCredits` in `task_5/js/main.ts`:


   - Each interface defines a number named `credits`
   - Add a brand property to each interface in order to uniquely identify each of them


- Create two functions named `sumMajorCredits` and `sumMinorCredits` in `task_5/js/main.ts`:


   - Each function takes two arguments `subject1` and `subject2`
   - `sumMajorCredits` returns `MajorCredits` value and `sumMinorCredits` returns `MinorCredits` value
   - Each function sums the credits of the two subjects



<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x04-TypeScript`
    - File: [`task_5/js/main.ts`](./task_5/js/main.ts)
    - File: [`task_5/package.json`](./task_5/package.json)
    - File: [`task_5/webpack.config.js`](./task_5/webpack.config.js)
    - File: [`task_5/tsconfig.json`](./task_5/tsconfig.json)
---


<br></br>
<div align="right">
    <sub style="font-style: italic"> Dean Robin Otsyeno - deanrobin777@gmail.com</sub>
</div>
