# Project
## **0x00. ES6 Basics**
---
## Table of Contents
- [Author Details](#author-details)
- [Project Description](#project-description)
- [Tasks](#tasks)
	- [0. Const or let?](#0)
	- [1. Block Scope](#1)
	- [2. Arrow functions](#2)
	- [3. Parameter defaults](#3)
	- [4. Rest parameter syntax for functions](#4)
	- [5. The wonders of spread syntax](#5)
	- [6. Take advantage of template literals](#6)
	- [7. Object property value shorthand syntax](#7)
	- [8. No need to create empty objects before adding in properties](#8)
	- [9. ES6 method properties](#9)
	- [10. For...of Loops](#10)
	- [11. Iterator](#11)
	- [12. Let's create a report object](#12)
	- [13. Iterating through report objects](#13)
	- [14. Iterate through object](#14)
---
## Author Details
- *Dean Robin Otsyeno - deanrobin777@gmail.com*

## Project Description


## Tasks
#### 0
###### [Table of Contents](#table-of-contents)
**0. Const or let?**

- Modify


   - function `taskFirst` to instantiate variables using `const`
   - function `taskNext` to instantiate variables using `let`


- Execution example:
```
export function taskFirst() {

  var task = 'I prefer const when I can.';
  return task;
}

export function getLast() {
  return ' is okay';
}

export function taskNext() {
  var combination = 'But sometimes let';
  combination += getLast();

  return combination;
}
bob@dylan:~$ cat 0-main.js

import { taskFirst, taskNext } from './0-constants.js';

console.log(`${taskFirst()} ${taskNext()}`);

bob@dylan:~$ 
bob@dylan:~$ npm run dev 0-main.js 
I prefer const when I can. But sometimes let is okay
bob@dylan:~$ 
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`0-constants.js`](./0-constants.js)
---
#### 1
###### [Table of Contents](#table-of-contents)
**1. Block Scope**

- Given what you’ve read about `var` and hoisting, modify the variables inside the function `taskBlock` so that the variables aren’t overwritten inside the conditional block.

- Execution:
```
export default function taskBlock(trueOrFalse) {

  var task = false;
  var task2 = true;

  if (trueOrFalse) {
    var task = true;
    var task2 = false;
  }

  return [task, task2];
}
bob@dylan:~$ cat 1-main.js

import taskBlock from './1-block-scoped.js';

console.log(taskBlock(true));
console.log(taskBlock(false));
bob@dylan:~$
bob@dylan:~$ npm run dev 1-main.js 
[ false, true ]
[ false, true ]
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`1-block-scoped.js`](./1-block-scoped.js)
---
#### 2
###### [Table of Contents](#table-of-contents)
**2. Arrow functions**

- Rewrite the following standard function to use ES6’s arrow syntax of the function `add` (it will be an anonymous function after)

- Execution:
```
export default function getNeighborhoodsList() {

  this.sanFranciscoNeighborhoods = ['SOMA', 'Union Square'];

  const self = this;
  this.addNeighborhood = function add(newNeighborhood) {
    self.sanFranciscoNeighborhoods.push(newNeighborhood);
    return self.sanFranciscoNeighborhoods;
  };
}
bob@dylan:~$ cat 2-main.js

import getNeighborhoodsList from './2-arrow.js';

const neighborhoodsList = new getNeighborhoodsList();
const res = neighborhoodsList.addNeighborhood('Noe Valley');
console.log(res);
bob@dylan:~$
bob@dylan:~$ npm run dev 2-main.js 
[ 'SOMA', 'Union Square', 'Noe Valley' ]
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`2-arrow.js`](./2-arrow.js)
---
#### 3
###### [Table of Contents](#table-of-contents)
**3. Parameter defaults**

- Condense the internals of the following function to 1 line - without changing the name of each function/variable. 

- Hint: The key here to define default parameter values for the function parameters.

- Execution:
```
export default function getSumOfHoods(initialNumber, expansion1989, expansion2019) {

  if (expansion1989 === undefined) {
    expansion1989 = 89;
  }

  if (expansion2019 === undefined) {
    expansion2019 = 19;
  }
  return initialNumber + expansion1989 + expansion2019;
}
bob@dylan:~$ cat 3-main.js

import getSumOfHoods from './3-default-parameter.js';

console.log(getSumOfHoods(34));
console.log(getSumOfHoods(34, 3));
console.log(getSumOfHoods(34, 3, 4));
bob@dylan:~$
bob@dylan:~$ npm run dev 3-main.js 
142
56
41
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`3-default-parameter.js`](./3-default-parameter.js)
---
#### 4
###### [Table of Contents](#table-of-contents)
**4. Rest parameter syntax for functions**

- Modify the following function to return the number of arguments passed to it using the rest parameter syntax

- Example:
- Execution:
```
export default function returnHowManyArguments() {


}
> returnHowManyArguments("Hello", "Holberton", 2020);

3
>
bob@dylan:~$ cat 4-main.js

import returnHowManyArguments from './4-rest-parameter.js';

console.log(returnHowManyArguments("one"));
console.log(returnHowManyArguments("one", "two", 3, "4th"));
bob@dylan:~$
bob@dylan:~$ npm run dev 4-main.js 
1
4
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`4-rest-parameter.js`](./4-rest-parameter.js)
---
#### 5
###### [Table of Contents](#table-of-contents)
**5. The wonders of spread syntax**

- Using spread syntax, concatenate 2 arrays and each character of a string by modifying the function below. Your function body should be one line long.

- Execution:
```
export default function concatArrays(array1, array2, string) {

}
bob@dylan:~$ cat 5-main.js

import concatArrays from './5-spread-operator.js';

console.log(concatArrays(['a', 'b'], ['c', 'd'], 'Hello'));

bob@dylan:~$
bob@dylan:~$ npm run dev 5-main.js 
[
  'a', 'b', 'c',
  'd', 'H', 'e',
  'l', 'l', 'o'
]
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`5-spread-operator.js`](./5-spread-operator.js)
---
#### 6
###### [Table of Contents](#table-of-contents)
**6. Take advantage of template literals**

- Rewrite the return statement to use a template literal so you can the substitute the variables you’ve defined.

- Execution:
```
export default function getSanFranciscoDescription() {

  const year = 2017;
  const budget = {
    income: '$119,868',
    gdp: '$154.2 billion',
    capita: '$178,479',
  };

  return 'As of ' + year + ', it was the seventh-highest income county in the United States'
        / ', with a per capita personal income of ' + budget.income + '. As of 2015, San Francisco'
        / ' proper had a GDP of ' + budget.gdp + ', and a GDP per capita of ' + budget.capita + '.';
}
bob@dylan:~$ cat 6-main.js

import getSanFranciscoDescription from './6-string-interpolation.js';

console.log(getSanFranciscoDescription());

bob@dylan:~$
bob@dylan:~$ npm run dev 6-main.js 
As of 2017, it was the seventh-highest income county in the United States, with a per capita personal income of $119,868. As of 2015, San Francisco proper had a GDP of $154.2 billion, and a GDP per capita of $178,479.
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`6-string-interpolation.js`](./6-string-interpolation.js)
---
#### 7
###### [Table of Contents](#table-of-contents)
**7. Object property value shorthand syntax**

- Notice how the keys and the variable names are the same?

- Modify the following function’s `budget` object to simply use the keyname instead.

- Execution:
```
export default function getBudgetObject(income, gdp, capita) {

  const budget = {
    income: income,
    gdp: gdp,
    capita: capita,
  };

  return budget;
}
bob@dylan:~$ cat 7-main.js

import getBudgetObject from './7-getBudgetObject.js';

console.log(getBudgetObject(400, 700, 900));

bob@dylan:~$
bob@dylan:~$ npm run dev 7-main.js 
{ income: 400, gdp: 700, capita: 900 }
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`7-getBudgetObject.js`](./7-getBudgetObject.js)
---
#### 8
###### [Table of Contents](#table-of-contents)
**8. No need to create empty objects before adding in properties**

- Rewrite the `getBudgetForCurrentYear` function to use ES6 computed property names on the `budget` object

- Execution:
```
function getCurrentYear() {

  const date = new Date();
  return date.getFullYear();
}

export default function getBudgetForCurrentYear(income, gdp, capita) {
  const budget = {};

  budget[`income-${getCurrentYear()}`] = income;
  budget[`gdp-${getCurrentYear()}`] = gdp;
  budget[`capita-${getCurrentYear()}`] = capita;

  return budget;
}
bob@dylan:~$ cat 8-main.js

import getBudgetForCurrentYear from './8-getBudgetCurrentYear.js';

console.log(getBudgetForCurrentYear(2100, 5200, 1090));

bob@dylan:~$
bob@dylan:~$ npm run dev 8-main.js 
{ 'income-2021': 2100, 'gdp-2021': 5200, 'capita-2021': 1090 }
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`8-getBudgetCurrentYear.js`](./8-getBudgetCurrentYear.js)
---
#### 9
###### [Table of Contents](#table-of-contents)
**9. ES6 method properties**

- Rewrite `getFullBudgetObject` to use ES6 method properties in the `fullBudget` object

- Execution:
```
import getBudgetObject from './7-getBudgetObject.js';


export default function getFullBudgetObject(income, gdp, capita) {
  const budget = getBudgetObject(income, gdp, capita);
  const fullBudget = {
    ...budget,
    getIncomeInDollars: function (income) {
      return `$${income}`;
    },
    getIncomeInEuros: function (income) {
      return `${income} euros`;
    },
  };

  return fullBudget;
}
bob@dylan:~$ cat 9-main.js

import getFullBudgetObject from './9-getFullBudget.js';

const fullBudget = getFullBudgetObject(20, 50, 10);

console.log(fullBudget.getIncomeInDollars(fullBudget.income));
console.log(fullBudget.getIncomeInEuros(fullBudget.income));

bob@dylan:~$
bob@dylan:~$ npm run dev 9-main.js 
$20
20 euros
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`9-getFullBudget.js`](./9-getFullBudget.js)
---
#### 10
###### [Table of Contents](#table-of-contents)
**10. For...of Loops**

- Rewrite the function `appendToEachArrayValue` to use ES6’s `for...of` operator. And don’t forget that `var` is not ES6-friendly.

- Execution:
```
export default function appendToEachArrayValue(array, appendString) {

  for (var idx in array) {
    var value = array[idx];
    array[idx] = appendString + value;
  }

  return array;
}
bob@dylan:~$ cat 10-main.js

import appendToEachArrayValue from './10-loops.js';

console.log(appendToEachArrayValue(['appended', 'fixed', 'displayed'], 'correctly-'));

bob@dylan:~$
bob@dylan:~$ npm run dev 10-main.js 
[ 'correctly-appended', 'correctly-fixed', 'correctly-displayed' ]
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`10-loops.js`](./10-loops.js)
---
#### 11
###### [Table of Contents](#table-of-contents)
**11. Iterator**

- Write a function named `createEmployeesObject` that will receive two arguments:


   - `departmentName` (String)
   - `employees` (Array of Strings)


- The function should return an object with the following format:
- Execution:
```
export default function createEmployeesObject(departmentName, employees) {


}
{

     $departmentName: [
          $employees,
     ],
}
bob@dylan:~$ cat 11-main.js

import createEmployeesObject from './11-createEmployeesObject.js';

console.log(createEmployeesObject("Software", [ "Bob", "Sylvie" ]));

bob@dylan:~$
bob@dylan:~$ npm run dev 11-main.js 
{ Software: [ 'Bob', 'Sylvie' ] }
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`11-createEmployeesObject.js`](./11-createEmployeesObject.js)
---
#### 12
###### [Table of Contents](#table-of-contents)
**12. Let's create a report object**

- Write a function named `createReportObject` whose parameter, `employeesList`, is the return value of the previous function `createEmployeesObject`.

- The method property receives `employeesList` and returns the number of departments. I would suggest suggest thinking back to the ES6 method property syntax.
- Execution:
```
export default function createReportObject(employeesList) {


}
{

  allEmployees: {
     engineering: [
          'John Doe',
          'Guillaume Salva',
     ],
  },
};
bob@dylan:~$ cat 12-main.js

import createEmployeesObject from './11-createEmployeesObject.js';
import createReportObject from './12-createReportObject.js';

const employees = {
    ...createEmployeesObject('engineering', ['Bob', 'Jane']),
    ...createEmployeesObject('marketing', ['Sylvie'])
};      

const report = createReportObject(employees);
console.log(report.allEmployees);
console.log(report.getNumberOfDepartments(report.allEmployees));

bob@dylan:~$
bob@dylan:~$ npm run dev 12-main.js 
{ engineering: [ 'Bob', 'Jane' ], marketing: [ 'Sylvie' ] }
2
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`12-createReportObject.js`](./12-createReportObject.js)
---
#### 13
###### [Table of Contents](#table-of-contents)
**13. Iterating through report objects**

- Write a function named `createIteratorObject`, that will take into argument a report Object created with the previous function `createReportObject`. 

- This function will return an iterator to go through every employee in every department.

- Execution:
```
export default function createIteratorObject(report) {


}
bob@dylan:~$ cat 100-main.js

import createIteratorObject from "./100-createIteratorObject.js";

import createEmployeesObject from './11-createEmployeesObject.js';
import createReportObject from './12-createReportObject.js';

const employees = {
    ...createEmployeesObject('engineering', ['Bob', 'Jane']),
    ...createEmployeesObject('marketing', ['Sylvie'])
};

const report = createReportObject(employees);

const reportWithIterator = createIteratorObject(report);

for (const item of reportWithIterator) {
    console.log(item);
}

bob@dylan:~$
bob@dylan:~$ npm run dev 100-main.js 
Bob
Jane
Sylvie
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`100-createIteratorObject.js`](./100-createIteratorObject.js)
---
#### 14
###### [Table of Contents](#table-of-contents)
**14. Iterate through object**

- Finally, write a function named `iterateThroughObject`. The function’s parameter `reportWithIterator` is the return value from `createIteratorObject`.

- It should return every employee name in a string, separated by `|`
- Should return `John Doe | Guillaume Salva`
- Reminder - the functions will be imported by the test suite.
- Full example:
- Execution:
```
 export default function iterateThroughObject(reportWithIterator) {


 }
{

  allEmployees: {
     engineering: [
          'John Doe',
          'Guillaume Salva',
     ],
  },
  ...
};
> employees = {

      ...createEmployeesObject('engineering', engineering),
      ...createEmployeesObject('design', design),
    };
>
> const report = createReportObject(employees);
> const reportWithIterator = createIteratorObject(report);
> iterateThroughObject(reportWithIterator)
'John Doe | Guillaume Salva | Kanye East | Jay Li'
> 
bob@dylan:~$ cat 101-main.js

import createEmployeesObject from "./11-createEmployeesObject.js";
import createReportObject from './12-createReportObject.js';
import createIteratorObject from './100-createIteratorObject.js';
import iterateThroughObject from './101-iterateThroughObject.js';


const employees = {
    ...createEmployeesObject('engineering', ['Bob', 'Jane']),
    ...createEmployeesObject('marketing', ['Sylvie'])
};

const report = createReportObject(employees);
const reportWithIterator = createIteratorObject(report);

console.log(iterateThroughObject(reportWithIterator));

bob@dylan:~$
bob@dylan:~$ npm run dev 101-main.js 
Bob | Jane | Sylvie
bob@dylan:~$
```

<br></br>
- Repo
    - GitHub repository: `alx-backend-javascript`
    - Directory: `0x00-ES6_basic`
    - File: [`101-iterateThroughObject.js`](./101-iterateThroughObject.js)
---


<br></br>
<div align="right">
    <sub style="font-style: italic"> Dean Robin Otsyeno - deanrobin777@gmail.com</sub>
</div>
