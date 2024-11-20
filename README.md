<div align="center">
  <img height="260" src="https://github.com/tsotneforester/infiniteJSTasks/assets/79293287/1cc7c4f6-0317-4e86-bead-11b50bc8cd97">

  <h1>🔰︱𝗶̲̅𝗻̲̅𝗳̲̅𝗶̲̅𝗻̲̅𝗶̲̅𝘁̲̅𝗲̲̅𝗝̲̅𝗦̲̅︱🔰 🚦︱🆃🅰🆂🅺🆂</h1>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&pause=1000&random=false&width=435&lines=Easy+%F0%9F%9F%A2+Medium+%F0%9F%9F%A1+Hard+%F0%9F%94%B4)](https://git.io/typing-svg)

</div>

<p>

[InfiniteJS](https://gpx.ge/infiniteJS/) has been developing in parallel with my web developer career. It was conceived as a more understandable alternative to our dear [Eloquent JavaScript](https://eloquentjavascript.net/), well... for beginners at least. Actually, it turned out to resembled a detective's notebook: practical for inner usage and bit abstract for outer glance. It went beyond JavaScript and covered almost every aspect I encountered in my career growth.

The origin of the tasks is very diverse: I had to thank [CS50](https://pll.harvard.edu/course/cs50-introduction-computer-science) for some of them, I encountered some in practice, and some... I tried to offer interesting and wonderful tasks. 👴🏻 We are starting to enjoy our own little successes! 🧲 🧁 ⚱️

</p>

> [!NOTE]  
> This repo was created in 2024, the tasks provided here are not based on the JavaScript syntax and behavior only, but any other languages can possibly handle them. Since JavaScript is my native programming language and most preferable one and since it as well as my knowledge has been constantly evolving, there are newer language features, newer and better solutions to problems here. Feel free to use them in the tasks! 😃 I would _really_ appreciate a reference to this repo, I gether the tasks and solutions and the community helps me so much to maintain and improve it! 💪🏼 Thank you and have fun! 🎉🎉🎉

<h5 align="center"><i>Please join my discord channel</i></h5>

<h5 align="center">

[![Discord](https://img.shields.io/discord/1027831568745648198?style=for-the-badge&logo=discord&logoColor=white&label=Discord&labelColor=%235865F2)](https://discord.gg/FMTkTe7q)

</h5>

| Algorithm         | Taks N |
| :---------------- | :-----: |
| Frequency Counter |   46, 29, 32, 3 , 53 |

---

### 🟢 01 - Hello Universe!

```javascript
console.log(sayHello()); // Hello Universe!

function sayHello() {
  //Write a function to generate greeting to the whole universe
}
```

<details><summary><b>Answer</b></summary>

```javascript
function sayHello() {
  return "Hello Universe!";
}
```

</details>

---

### 🟢 02 - Super Mario

Do you remember Nintendo’s Super Mario Brothers? Mario must ascend a bunch of right-aligned, left-aligned pyramid of blocks. You must write function, that will receive number from 1 to 9 and build that height pyramids in console, use "#" as building block.

```javascript
buildRightAligned(5);
// #
// ##
// ###
// ####
// #####
buildLeftAligned(5);
//     #
//    ##
//   ###
//  ####
// #####
buildPyramid(5);
//     ##
//    ####
//   ######
//  ########
// ##########
```

<details><summary><b>Answer</b></summary>

```javascript


function buildRightAligned(height) {
  for (let i = 1; i <= height; i++) {
    console.log("#".repeat(i));
  }
}

function buildRightAligned(height) {
  let result = '';
  for (let i = 0; i <= height; i++) {
    result += '#';
    console.log(result);
  }
}

function buildRLeftAligned(height) {
    for (let i = 1; i <= height; i++) {
        console.log(' '.repeat(height - i) + '#'.repeat(i));
    }
}


function buildPyramid(height) {
    for (let i = 1; i <= height; i++) {
        let spaces = ' '.repeat(height - i);
        let blocks = '#'.repeat(i);
        console.log(spaces + blocks + ' ' + blocks);
    }
}
```

</details>

### 🟢 03 - Mode

```javascript
const results = [3, "a", "a", "a", 2, 3, "a", 3, "a", 2, 4, 9, 3];
console.log(getMode(results)); //a - 5 times

function getMode(array) {
  //Write a function to find the most frequent item of an array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getMode(arr) {
  let frequencyObject = {};

  for (const element of arr) {
    frequencyObject[element] = (frequencyObject[element] || 0) + 1;
  }

  let maxFrequency = 0;
  let character = "";

  for (const key in frequencyObject) {
    if (frequencyObject[key] > maxFrequency) {
      maxFrequency = frequencyObject[key];
      character = key;
    }
  }

  return `${character} - ${maxFrequency} times`;
}
```

</details>

---

### 🟢 04 - Toggle Case

```javascript
let str = "Brown Fox";
console.log(caseToggler(str)); //bROWN fOX

function caseToggler(string) {
  //Write a function which accepts string as argument and swaps the case of each character.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function caseToggler(string) {
  let result = "";

  for (const char of string) {
    if (char == char.toUpperCase()) {
      result += char.toLowerCase();
    } else {
      result += char.toUpperCase();
    }
  }

  return result;
}

```

</details>

---

### 🟢 05 - Duplicate Remove (string)

```javascript
const cars = ["Mini", "mini", "fiat", "fiat", "bmw", "mini", "OPEL", "Mini", "opel", "OPEL", "Mini", "bmw", "opel", "OPEL", "bmw", "opel", "bmw", "mini", "opel", "bmw", "fiat", "OPEL", "fiat", "bmw"];

console.log(duplicateRemover(cars));
// 1️⃣ ['Mini', 'mini', 'fiat', 'bmw', 'OPEL', 'opel']
// 2️⃣ ["mini", "fiat", "bmw", "opel"]

function dublicateRemover(arr) {
  //Write a function to remove duplicate items from array (case-sensitive/case-insensitive)
  //⭐ - can you think of method-less solution?
}
```

<details><summary><b>Answer</b></summary>

```javascript
function duplicateRemover(arr) {
  return arr.filter((e, i) => {
    return arr.indexOf(e) === i;
    //return arr.indexOf(e.toLowerCase()) === i;
  });
}
```

```javascript
function duplicateRemover(arr) {
  return [...new Set(arr)];
  //return [...new Set(arr.map((e) => e.toLowerCase()))];
}
```

⭐ method-less solution

```javascript
function duplicateRemover(arr) {
  let obj = {};

  for (let i = 0; i < arr.length; i++) {
    obj[arr[i]] = null;
    //obj[arr[i].toLowerCase()] = null;
  }

  let result = [];

  for (let key in obj) {
    result.push(key);
  }

  return result;
}
```

</details>

---

### 🟢 06 - Duplicate Finder

```javascript
const nums = [1, 2, -2, 4, 5, 4, 7, 8, 7, 7];
console.log(duplicateFinder(nums)); //["4", "7"];

function duplicateFinder(arr) {
  //Write a function to get array of duplicate values in array.
}
```

<details><summary><b>Answer</b></summary>
  
version 1
```javascript
function cateFinder(arr) {
  let result = arr.filter((e, index) => {
    return arr.indexOf(e) !== index;
  });
  return [...new Set(result)];
}
```
version 2
```javascript
function duplicateFinder(arr) {
  return arr.reduce((acc, cur, i) => {
    if (arr.lastIndexOf(cur) !== i && !acc.includes(cur)) {
      acc.push(cur);
    }
    return acc;
  }, []);
}
```

</details>

---

### 🟡 07 - Aggregate

```javascript
const num1 = [1, 25, 0, 8, 9];
const num2 = [3, 5, 6, 7, 8];
const num3 = [3, 13];
console.log(aggregrate(num1, num2, num3));
//[7, 43, 6, 15, 17]

function aggregrate(...arr) {
  //write a function to compute the sum of each individual index value from the given arrays.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function aggregrate(...arr) {
  let args = [...arr]; // arguments array
  let arrayLengths = args.map((e) => {
    return e.length;
  }); // array of argument array lengthes

  let padLength = Math.max(...arrayLengths);

  const AggArray = Array.from({ length: padLength }, (_, i) => {
    return 0;
  }); // [0, 0, 0, 0, 0]

  for (let i = 0; i < padLength; i++) {
    args.forEach((e) => {
      AggArray[i] += e[i] || 0;
    });
  }

  return AggArray;
}

function aggregrate(...n) {
  const array = [];
  for (let i = 0; i < n.length; i++) {
    for (let y = 0; y < n[i].length; y++) {
      array[y] === undefined ? array.push(0) : null;
      array[y] += n[i][y];
    }
  }
  return array;
}
```

</details>

---

### 🟢 08 - Union

```javascript
const num1 = [1, 2, 3];
const num2 = [6, 2, 1];
const num3 = [8, 2, 1];
const num4 = [3, 5, 1];
console.log(union(num1, num2, num3, num4)); // [1, 2, 3, 6, 8, 5]

function union(...arr) {
  //Write a function to compute the union of given arrays with only unique items.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function union(...arr) {
  let newSet = new Set([...arr].flat());
  return [...newSet];
}
```

</details>

---

### 🟢 09 - Numberify

```javascript
const array = [NaN, 0, 15, false, -22, "", undefined, 47, null, [5, 7]];
console.log(numberify(array)); //[0, 15, -22, 47]

function numberify(arr) {
  //Write a function to retrieve only numbers from given array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function numberify(arr) {
  return arr.filter((e) => {
    return typeof e === "number" && !isNaN(e);
  });
}
```

</details>

---

### 🟢 10 - Remove Item

```javascript
const num = [2, 5, 9, 7, 8, 5, 6];
console.log(removeItem(num, 5)); // [2, 9, 7, 8, 6];

function removeItem(array, item) {
  //Write a function to remove a specified item from given array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function removeItem(array, item) {
  return array.filter((elem) => elem !== item);
}
```

</details>

---

### 🟢 11 - Array Gen.

```javascript
console.log(arrayGenerator(6, 5, 2)); //[6, 8, 10, 12, 14]

function arrayGenerator(start, length, step) {
  //Write a function to generate array of specified start item, length and increasing by given number
}
```

<details><summary><b>Answer</b></summary>

```javascript
function arrayGenerator(start, length, step) {
  let newArr = [start];

  for (let i = 0; i < length - 1; i++) {
    newArr.push(newArr[i] + step);
  }

  return newArr;
}
```

</details>

---

### 🟢 12 - GPX

```javascript
const arr = ["G", "P", "X"];
console.log(fillArr(arr, 5)); //["G", "P", "X", "G", "P"]

function fillArr(arr, n) {
  //Write a function which returns array of 'n' length with given array pattern repeating
}
```

<details><summary><b>Answer</b></summary>

```javascript
function fillArr(arr, n) {
  let emptyArr = Array.from({ length: n });
  return emptyArr.fill(arr).flat().splice(0, n);
}
```

</details>

---

### 🟢 13 - Vlookup

```javascript
const genres = [
  {
    id: 28,
    name: "Action",
  },
  {
    id: 12,
    name: "Adventure",
  },
  {
    id: 14,
    name: "Thriller",
  },
  {
    id: 21,
    name: "Drama",
  },
];
let ids = [28, 21];

console.log(vlookup(ids, genres)); //['Action', 'Drama']

function vlookup(ids, data) {
  //Write a function to generate array of movie ganre names from given ganre id array and ganres data
}
```

<details><summary><b>Answer</b></summary>

```javascript
function vlookup(ids, data) {
  let result = [];

  ids.forEach((value) => {
    data.forEach((e) => {
      if (value === e.id) {
        result.push(e.name);
      }
    });
  });
  return result;
}
```

</details>

---

### 🟢 14 - Odd index

```javascript
const numbers = [23, 42, 14, 57, 67, 69, 78];
console.log(getOddIndex(numbers)); //[0, 3, 4, 5]

function getOddIndex(arr) {
  //Write a function to generate array of indexes of odd numbers in given array
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getOddIndex(arr) {
  let temp = [];
  arr.forEach((e, i) => {
    if (e % 2 == 1) {
      temp.push(i);
    }
  });
  return temp;
}
```

</details>

---

### 🟢 15 - Exclude

```javascript
let arr1 = [1, 2, 3, 4, 5, 6];
let arr2 = [5, 6, 7, 8, 9];

console.log(overlapExclude(arr1, arr2)); //[1, 2, 3, 4]

function overlapExclude(f, l) {
  //Write a function That returns array of numbers from first given array that are not presented in last array
}
```

<details><summary><b>Answer</b></summary>

```javascript
function overlapExclude(f, l) {
  return f.filter((num) => {
    if (l.indexOf(num) == -1) {
      return num;
    }
  });
}
```

</details>

---

### 🟢 16 - Senior

```javascript
const members = [
  [18, 20], //[age, working experience]
  [45, 2],
  [61, 12],
  [37, 6],
  [21, 21],
  [78, 9],
];

console.log(openOrSenior(members)); //["Open", "Open", "Senior", "Open", "Open", "Senior"];

function openOrSenior(data) {
  // To be a senior, a member must be at least 55 years old and have working experience more than 7 years. Write a function to determine wheather member is Senior or Open
}
```

<details><summary><b>Answer</b></summary>

```javascript
function openOrSenior(data) {
  return data.map((e) => {
    return e[0] >= 55 && e[1] > 7 ? "Senior" : "Open";
  });
}
```

</details>

---

### 🟢 17 - Reduce Deposite

```javascript
let deposits = [200, 450, -400, 3000, -650, -130, 70, 1300, 5000, 3400, -150, -790, -3210, -1000, 8500, -30, 200, -200, 340, -300, -20, 50, 400, -460, 430, 1000, 700, 50, 90];

console.log(depositsAbove(1000, deposits)); // 5

function depositsAbove(num, data) {
  //Write a function to count deposits above given number for given array of deposits. use reduce() method
}
```

<details><summary><b>Answer</b></summary>

```javascript
function depositsAbove(num, data) {
  return data.reduce((count, cur) => (cur > num ? ++count : count), 0);
}
```

</details>

---

### 🟢 18 - Titlecase

```javascript
const exceptions = ["a", "an", "and", "the", "but", "or", "on", "in", "with", "of"];

console.log(convertTitleCase("this is a nice title of great writer"));
console.log(convertTitleCase("and then there were NONE"));

// result: "This Is a Nice Title of Great Writer"
// result: "And Then There Were None"

function convertTitleCase(string) {
  // Write a function that transfers every word but exceptions to uppercase. Let's assume that given string has no excessive spaces.
  // 🌟 If you'd like, implement solution that handles excessive spaces
}
```

<details><summary><b>Answer</b></summary>

```javascript
function convertTitleCase(string) {
  const capitzalize = (str) => str[0].toUpperCase() + str.slice(1);

  const tempString = string
    .toLowerCase()
    .split(" ")
    .map((word) => (exceptions.includes(word) ? word : capitzalize(word)))
    .join(" ");

  return capitzalize(tempString);
}
```

</details>

---

### 🟢 19 - Trimmer

```javascript
const string = "   This  is   a    test.  ";

console.log(trimmer(string)); //This is a test.

function trimmer(str) {
  // Write a function that removes exessive spaces from string
}
```

<details><summary><b>Answer</b></summary>

```javascript
function trimmer(str) {
  return str.replace(/ {2,}/g, " ").trim();
}
```

</details>

---

### 🟡 20 - Chess Board

```javascript
const whiteSquare = "☐";
const BlackSquare = "☒";

console.log(chessify(8));

// ☐☒☐☒☐☒☐☒
// ☒☐☒☐☒☐☒☐
// ☐☒☐☒☐☒☐☒
// ☒☐☒☐☒☐☒☐
// ☐☒☐☒☐☒☐☒
// ☒☐☒☐☒☐☒☐
// ☐☒☐☒☐☒☐☒
// ☒☐☒☐☒☐☒☐

function chessify(size) {
  //Write a function to create chess board in console
}
```

<details><summary><b>Answer</b></summary>

```javascript
function chessify(size) {
  let node = "";
  for (let horizontalLine = 1; horizontalLine <= size; horizontalLine++) {
    let lineNode = "";
    for (let verticalLine = 0; verticalLine < size; verticalLine++) {
      if (horizontalLine % 2 == 1) {
        verticalLine % 2 == 0 ? (lineNode += whiteSquare) : (lineNode += BlackSquare);
      } else {
        verticalLine % 2 == 0 ? (lineNode += BlackSquare) : (lineNode += whiteSquare);
      }
    }

    node += lineNode + "\n";
  }
  return node;
}
```

</details>

---

### 🟢 21 - Filter Properties

```javascript
const users = [
  {
    id: "64ede4012b31077af2ded83e",
    name: "Gould Daniels",
    address: "Agate Court, Clarksburg",
    balance: "$277.49",
    age: 20,
    registered: "2017-11-23T10:31:14",
  },
  {
    id: "64ede401d067f20dbc0ea8c3",
    name: "Paula Henderson",
    address: "Lawton Street, Zarephath",
    balance: "$322.43",
    age: 12,
    registered: "2017-01-13T07:36:37",
  },
];

const allowed = ["id", "name", "age"];

console.log(filterIn(users, allowed));

// [
//   {
//     id: "64ede4012b31077af2ded83e",
//     name: "Gould Daniels",
//     age: 20,
//   },
//   {
//     id: "64ede401d067f20dbc0ea8c3",
//     name: "Paula Henderson",
//     age: 12,
//   },
// ];

function filterIn(data, arr) {
  // Write a function that will remove properties from array of objects, other than specified in given array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function filterIn(data, arr) {
  for (let obj of data) {
    Object.keys(obj)
      .filter((i) => !arr.includes(i))
      .forEach((e) => delete obj[e]);
  }

  return data;
}
```

</details>

---

### 🟢 22 - Filter Out Properties

```javascript
const users = [
  {
    id: "64ede4012b31077af2ded83e",
    name: "Gould Daniels",
    address: "Agate Court, Clarksburg",
    balance: "$277.49",
    age: 20,
    registered: "2017-11-23T10:31:14",
  },
  {
    id: "64ede401d067f20dbc0ea8c3",
    name: "Paula Henderson",
    address: "Lawton Street, Zarephath",
    balance: "$322.43",
    age: 12,
    registered: "2017-01-13T07:36:37",
  },
];

const toBeDeleted = ["address", "balance", "registered"];

console.log(filterOut(users, toBeDeleted));

// [
//   {
//     id: "64ede4012b31077af2ded83e",
//     name: "Gould Daniels",
//     age: 20,
//   },
//   {
//     id: "64ede401d067f20dbc0ea8c3",
//     name: "Paula Henderson",
//     age: 12,
//   },
// ];

function filterOut(data, arr) {
  // Write a function that will remove properties from array of objects specified in given array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function filterOut(data, arr) {
  for (let obj of data) {
    arr.forEach((e) => delete obj[e]);
  }
  return data;
}
```

</details>

---

### 🟢 23 - Unique Colors

```javascript
const users = [
  {
    id: "64ede4012b31077af2ded83e",
    name: "Gould Daniels",
    color: ["#074454", "#364f08", "#ad62a4"],
  },
  {
    id: "64ede401d067f20dbc0ea8c3",
    name: "Paula Henderson",
    color: ["#490525", "#074454", "#525946"],
  },
];

console.log(uniqueColors(users, "color"));
//["#074454", "#364f08", "#ad62a4", "#490525", "#525946"]

function uniqueColors(data, key) {
  //Write a function that will collect unique values of given object key
}
```

<details><summary><b>Answer</b></summary>

```javascript
function uniqueColors(data, key) {
  return [...new Set(data.map((obj) => obj[key]).flat())];
}
```

</details>

---

### 🔴 24 - DNA

inspired by [CS50](https://cs50.harvard.edu/x/2024/psets/6/dna/) :books:

```javascript
const DNA = "GGGGAATATGGTTATTAAGTTAAAGAGAAAGAAAGATGTGGGTGATATTAATGAATGAATGAATGAATGAATGAATGAATGTTATGATAGAAGGATAAAAATTAAATAAAATTTTAGTTAATAGAAAAAGAATATATAGAGATCAGATCTATCTATCTATCTTAAGGAGAGGAAGAGATAAAAAAATATAATTAAGGAA";

const STR = "AATG"; //Short Tandem Repeats

console.log(getMaxSequence(DNA, STR)); // 8

// AGATC 2
// AATG 8
// TATC 3

function getMaxSequence(str, subStr) {
  // Write a function which returns longest consecutive sequence of substring in string
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getMaxSequence(str, subStr, indexes = [], startIdx = 0) {
  const index = str.indexOf(subStr, startIdx);
  if (index !== -1) {
    indexes.push(index);
    getMaxSequence(str, subStr, indexes, index + subStr.length);
  }

  let counter = 0; // to store longest sequence of repeating STR
  let currentCounter = 0; // current sequence of repeating STR
  indexes.forEach((e, i) => {
    if (indexes[i + 1] - e == subStr.length) {
      currentCounter++;
    } else {
      if (currentCounter > counter) {
        counter = currentCounter;
      }
      currentCounter = 0;
    }
  });

  return counter + 1;
}
```

</details>

---

### 🟡 25 - Array of Indexes

```javascript
const quote = "Education never ends, Watson!";
console.log(getIndexes(quote, "on")); // [7, 26]

function getIndexes(text, str) {
  //Write a function to generate array of substring indexes in given quote
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getIndexes(text, str) {
  let indexes = [];
  let i = -1;
  while (text.indexOf(str, i + 1) != -1) {
    i = text.indexOf(str, i + 1);
    indexes.push(i);
  }

  return indexes;
}
```

</details>

---

### 🟢 26 - Reduced Array

```javascript
const flags = ["ARM", "AZR", "GEO", "GEO", "TUR", "GEO"];
console.log(getIndexes(flags, "GEO")); //[2, 3, 5]

function getIndexes(arr, str) {
  //Write a function to generate array of indexes of given string in given array. .reduce is preferable
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getIndexes(arr, str) {
  return arr.reduce((acc, e, i) => {
    if (e == str) {
      acc.push(i);
    }
    return acc;
  }, []);
}
```

</details>

---

### 🟢 27 - Common Items

```javascript
const arr1 = [1, 2, 3, 4, 5, 6];
const arr2 = [5, 6, 7, 8, 9];
console.log(findCommonItems(arr1, arr2)); //[5, 6]

function findCommonItems(a, b) {
  //Write a function to generate array of items common for pair of given arrays
}
```

<details><summary><b>Answer</b></summary>

```javascript
function findCommonItems(a, b) {
  return a.filter((num) => {
    if (b.includes(num)) {
      return num;
    }
  });
}
```

</details>

---

### 🟡 28 - Bulk Overlaping

```javascript
const array = [
  [1, 2, 3, 4],
  [3, 4, 5, 6],
  [2, 3, 4, 7],
];
console.log(bulkOverlaping(array)); // [3, 4]

function bulkOverlaping(arr) {
  //Write a function to generate array of items common for arrays inside given array
}
```

<details><summary><b>Answer</b></summary>

```javascript
function bulkOverlaping(arr) {
  const commonNumbers = [];

  for (let i = 0; i < arr[0].length; i++) {
    if (arr.every((array) => array.includes(arr[0][i]))) {
      commonNumbers.push(arr[0][i]);
    }
  }

  return commonNumbers;
}

function bulkOverlaping(arr) {
  let commonNumbers = arr.reduce((acc, e) => {
    e.forEach((item) => {
      if (arr.every((array) => array.includes(item))) {
        acc.push(item);
      }
    });
    return acc;
  }, []);

  return [...new Set(commonNumbers)];
}
```

</details>

---

### 🟢 29 - Anagrams

An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

```javascript
const word1 = "Listen";
const word2 = "silent";
console.log(areAnagrams(word1, word2)); // true

function areAnagrams(word1, word2) {
  //Write a function to find if given words are anagrams.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function areAnagrams(word1, word2) {
  const sortedWord1 = [...word1.toLowerCase()].sort().join("");
  const sortedWord2 = [...word2.toLowerCase()].sort().join("");

  return sortedWord1 === sortedWord2;
}
```
more sophistaced solution
```javascript
function areAnagrams(word1, word2) {
  if (word1.length != word2.length) {
    return false;
  }

  let counter1 = {};
  let counter2 = {};

  for (const letter of word1.toLowerCase()) {
    counter1[letter] = (counter1[letter] || 0) + 1;
  }

  for (const letter of word2.toLowerCase()) {
    counter2[letter] = (counter2[letter] || 0) + 1;
  }

  //console.log(counter1);
  //console.log(counter2);

  for (const letter in counter1) {
    if (counter1[letter] != counter2[letter]) {
      return false;
    }
  }

  return true;
}
```

</details>

---

### 🟢 30 - Sum Up to Zero

```javascript
const array = [-5, -4, -3, 0, 2, 5, 8, 9];
console.log(hasZeroSumPair(array));

function hasZeroSumPair(arr) {
  //Write a function that will return boolean "TRUE", if it finds 2 numbers in given array, which sums up to zero
  //consider: -0 === 0 is true in JS
}
```

<details><summary><b>Answer</b></summary>

```javascript
function hasZeroSumPair(arr) {
  for (let num of arr) {
    if (num === 0 && num === -0) continue;
    // as (-0 === 0) is true in JS, we must skip 0 in iteration

    if (arr.includes(-num)) {
      return true;
    }
  }
  return false;
}
```

</details>

---

### 🟢 31 - Objectify

```javascript
const keys = ["name", "age", "country"];
const values = ["Tom", 29, "Poland"];

console.log(objectify(keys, values));
// {name: 'Tom', age: 29, country: 'Poland'}

function objectify(arr1, arr2) {
  //Write a function that creates object with key names for given 1st array and values from given 2nd array
}
```

<details><summary><b>Answer</b></summary>
1. Nice-n-easy solution
  
```javascript
function objectify(arr1, arr2) {
  let obj = {};
  arr1.forEach((e, i) => {
    obj[e] = arr2[i];
  });
  return obj;
}
```

2. More advanced technics

```javascript
function objectify(arr1, arr2) {
  return Object.fromEntries(
    arr1.reduce((acc, __, i) => {
      acc.push([arr1[i], arr2[i]]);
      return acc;
    }, [])
  );
}
```

</details>

---

### 🟢 32 - Equal Arrays

```javascript
let array1 = [1, 5, 3, 2];
let array2 = [5, 2, 3, 1];

console.log(isEqual(array1, array2));

function isEqual(arr1, arr2) {
  //write a function, that checks if 2 number arrays are equal
}
```

<details><summary><b>Answer</b></summary>

```javascript
function isEqual(arr1, arr2) {
  //avoid execution when not equly-sized arrays
  if (arr1.length != arr2.length) return false;

  const frequencies = {};

  for (let i = 0; i < arr1.length; i++) {
    let element1 = arr1[i];
    let element2 = arr2[i];

    frequencies[element1] = (frequencies[element1] || 0) + 1;
    frequencies[element2] = (frequencies[element2] || 0) - 1;
  }

  for (let key in frequencies) {
    if (frequencies[key] !== 0) return false;
  }
  return true;
}
````

</details>

---

### 🔴 33 - Spam Detector

```javascript
const inbox = [
  { from: "alice@beer.com", to: "bob@code.com", subject: "Urgent Meeting Required", body: "We need to discuss the project milestones." },
  { from: "carol@tech.com", to: "dan@developer.com", subject: "System Update Report", body: "Please fix this critical bug ASAP." },
  { from: "eve@company.com", to: "frank@client.com", subject: "Project Deadline Approaching", body: "Please review the project timeline." },
  { from: "grace@management.com", to: "beer@project.com", subject: "Quick Sync", body: "We are out of supplies, please restock!" },
  { from: "ivan@development.com", to: "judy@bugs.com", subject: "Code Review", body: "Let’s ensure our code is clean and maintainable." },
  { from: "kyle@support.com", to: "laura@customer.com", subject: "Update on Support Ticket", body: "Your issue will be resolved before the bedtime." },
];
const spam = ["beer", "bug", "deadline"];

console.log(spamDetector(spam, inbox));
//all objects get 'spam: true' but LAST ONE, as none on the words are found in last object

function spamDetector(words, objects) {
  // Write a function with 2 arguments (array of words and array of objects) that will check every object properties against given words (case insensitive) and if found, will add "spam:true" property to that object
  //TIP: This is all about loops, as we have 3 words, 6 objects and 4 properties in each, total of 72 iterations will occur. Try to avoid excessive ones by 2 way optimization: 1) when iterating object properties, with early match, there is no need to go through all properties 2) as object already has 'spam: true' property, we can skip it.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function spamDetector(words, objects) {
  let status = true;

  for (const word of words) {
    for (const object of objects) {
      if (object.spam == undefined) {
        for (const key in object) {
          status = String(object[key]).toLowerCase().includes(word);
          if (status) break;
        }
        if (status) {
          object.spam = status;
        }
      }
    }
  }
  return objects;
}
```

</details>

---

### 🟢 34 - Reverse Array

```javascript
const arr = ["A", "C", "B"];
console.log(reverseArray(arr));
// → ["B", "C", "A"];

function reverseArray(arr) {
  // Write a function which will reverse sequence of array items. reverse() is too simple, isn't it?
}
```

<details><summary><b>Answer</b></summary>

```javascript
function reverseArray(arr) {
  let newArr = [];

  for (let i = arr.length - 1; i >= 0; i--) {
    newArr.push(arr[i]);
  }

  return newArr;
}
```

super short version

```javascript
function reverseArray(arr) {
  return arr.map((_, i, arr) => arr[arr.length - i - 1]);
}
```

</details>

---

### 🟢 35 - Reverse String

```javascript
const string = "i'm gonna win";
console.log(stringReverse(string)); //niw annog m'i

function stringReverse(str) {
  // Write a function which will reverse given string
}
```

<details><summary><b>Answer</b></summary>

```javascript
function stringReverse(str) {
  return str
    .split("")
    .map((_, i, r) => r[r.length - i - 1]) // .reverse()
    .join("");
}
```

</details>

---

### 🟢 36 - Palindrome Word

```javascript
function isPalindrome(word) {
  // Write a function which will check if given word is a palindrome
  //💡 A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.
  //🔰 You'll need to remove all non-alphanumeric characters (punctuation, spaces and symbols) and turn everything into the same case (lower or upper case) in order to check for palindromes
}


console.log(isPalindrome("e_ yE")); //true
console.log(isPalindrome("A man, a plan, a canal. Panama")); //true
console.log(isPalindrome("never odd or even")); //true
```

<details><summary><b>Answer</b></summary>

```javascript
function isPalindrome(word) {
  let filtered = word.replace(/[^a-zA-Z0-9]/g, "").toLowerCase();
  return filtered === filtered.split("").reverse().join("");
}
```

</details>

---

### 🟡 37 - Sliding Sum

```javascript
const array = [1, 3, 7, 5, 6, 4, 9, 1];
const num = 4;

console.log(maxSubarraySum(array, num)); // 24

function stringReverse(str) {
  // Write a function which will calculate from given array and integer maximum given-number-sized-subarray sum
  //[1, 3, 7, 5] - 16 ❌
  //[3, 7, 5, 6] - 21 ❌
  //[7, 5, 6, 4] - 22 ❌
  //[5, 6, 4, 9] - 24 ✔️
  //[6, 4, 9, 1] - 20 ❌
  // 💡: "sliding window" algorithm is best solution here, try to guess most ergonomic and mathematical solution or at least solve it
}
```

<details><summary><b>Answer</b></summary>
  
version 1 (very casual)
```javascript
function maxSubarraySum(arr, size) {
  if (size > arr.length) {
    return null;
  }

const subArraysCount = arr.length - size + 1;
//count number of arrays of {size} neighbouring numbers

const arrayOfArrays = [];
for (let i = 0; i < subArraysCount; i++) {
let tempArrayOfSize = [];
for (let ii = i; ii < size + i; ii++) {
tempArrayOfSize.push(arr[ii]);
}
arrayOfArrays.push(tempArrayOfSize);
}
//nested loop to generate array of arrays of {size} neighbouring numbers
//[[1, 3, 7, 5], [3, 7, 5, 6],....]

const ArrayOfSums = arrayOfArrays.map((e) => {
return e.reduce((acc, cur) => {
return acc + cur;
}, 0);
});
//array of summed sub arrays

return Math.max(...ArrayOfSums);
}

````
version 2 ("Sliding Window" pattern)

```javascript
function maxSubarraySum(arr, size) {
  if (size > arr.length) {
    return null;
  }

  let maxSum = 0;
  let tempSum = 0;

  // initialize the window
  for (let i = 0; i < num; i++) {
    maxSum += arr[i];
  }

  tempSum = maxSum;

  // slide the window over the array
  for (let i = num; i < arr.length; i++) {
    tempSum = tempSum - arr[i - num] + arr[i];
    maxSum = Math.max(maxSum, tempSum);
  }

  return maxSum;
}
````

</details>

---

### 🟢 38 - Vowels & Consonants

```javascript
const string = "innovation";
console.log(countVowelsAndConsonants(string)); //{vowels: 5, consonants: 5}

function countVowelsAndConsonants(word) {
  // Write a function which will count vowels and consonants in the given word
}
```

<details><summary><b>Answer</b></summary>

```javascript
function countVowelsAndConsonants(word) {
  const vowelsArr = ["i", "e", "o", "u", "a"];

  let arr = word.toLowerCase().split("");

  let vowels = 0;
  let consonants = 0;

  for (let i = 0; i < arr.length; i++) {
    if (vowelsArr.includes(arr[i])) {
      vowels++;
    } else {
      consonants++;
    }
  }

  return { vowels, consonants };
}
```

</details>

---

### 🟢 39 - Unique Keys

```javascript
const arrayOfObjects = [
  { name: "Ann", age: 25, city: "Paris" },
  { name: "Thomas", age: 30, country: "USA" },
  { name: "Salomea", city: "Tbilisi", occupation: "Engineer" },
];
console.log(uniqueKeys(arrayOfObjects));
// ['name', 'age', 'city', 'country', 'occupation']

function uniqueKeys(arr) {
  // Write a function to generate array of unique keys from given array of objects
}
```

<details><summary><b>Answer</b></summary>

```javascript
function uniqueKeys(arr) {
  const allKeys = arr.flatMap((e) => Object.keys(e));
  return [...new Set(allKeys)];
}
```

</details>

---

### 🟢 40 - Pangram Check

```javascript
const string1 = "The quick brown fox jumps over the lazy dog";
const string2 = "Waltz, bad nymph, for quick jigs vex.";
const string3 = "The five boxing wizard jump quickly.";

console.log(isPangram(string1)); // ✔️ true
console.log(isPangram(string2)); // ✔️ true
console.log(isPangram(string3)); // ❌ false (missing 's')

function isPangram(sentence) {
  // Write a function to checks if given string is pangram
  //💡 A pangram or holoalphabetic sentence is a sentence using every letter of a given alphabet at least once.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function isPangram(sentence) {
  let arr = [
    ...new Set(
      sentence
        .toLowerCase()
        .replace(/[^a-z]/g, "") // removes non-letter characters
        .split("")
    ),
  ];
  return arr.length == 26;
}
```

```javascript
function isPangram(sentence) {
  sentence = sentence.toLowerCase();

  const alphabetSet = new Set();

  for (const char of sentence) {
    if (/[a-z]/.test(char)) {
      alphabetSet.add(char);
    }
  }

  return alphabetSet.size === 26;
}
```

</details>

---

### 🟢 41 - Unique Letters Count

```javascript
console.log(countUniqueLetters("Mississippi")); // { m: 1, i: 4, s: 4, p: 2 }

function countUniqueLetters(str) {
  //Write a function that coutns unique letters in string
}
```

<details><summary><b>Answer</b></summary>

```javascript
function countUniqueLetters(str) {
  str = str.toLowerCase();
  const letterCounts = {};

  // Iterate through each character in the word
  for (const char of str) {
    // Check if the character is a letter (a-z)
    if (/[a-z]/.test(char)) {
      // If the letter exists in the object, increment its count
      if (letterCounts[char]) {
        letterCounts[char]++;
      } else {
        // If the letter is new, initialize its count to 1
        letterCounts[char] = 1;
      }
    }
  }

  return letterCounts;
}
```

</details>

---

### 🟢 42 - Unique Numbers

```javascript
const couples = [10, 5, 10, 7, 5, 12, 13];
console.log(findUniqueNumbers(couples)); // [7, 12, 13]

function findUniqueNumbers(arr) {
  //Write a function that creates array on unique number in given array
}
```

<details><summary><b>Answer</b></summary>

```javascript
function findUniqueNumbers(arr) {
  return arr.reduce((acc, cur) => {
    if (arr.lastIndexOf(cur) == arr.indexOf(cur)) {
      acc.push(cur);
    }
    return acc;
  }, []);
}
```

```javascript
function findUniqueNumbers(arr) {
  const numberCounts = {};

  // Iterate through the array and count occurrences
  for (const num of arr) {
    if (numberCounts[num]) {
      numberCounts[num]++;
    } else {
      numberCounts[num] = 1;
    }
  }

  return arr.filter((num) => numberCounts[num] === 1);
}
```

</details>

---

### 🟢 43 - Count Nested

```javascript
const numbers = [2, 8, [6, 3, 3], [4], 5, [3, 4, [5, 4]]];
console.log(arrayCounter(numbers)); // 3

function arrayCounter(arr) {
  //Write a function to count number of first-level nested arrays
}
```

<details><summary><b>Answer</b></summary>

```javascript
function arrayCounter(arr) {
  return arr.filter((n) => Array.isArray(n)).length;
}
```

</details>

---

### 🟢 44 - Remove Element

```javascript
const myArray = [1, 3, 2, 2, 3, 2];
console.log(removeElement(myArray, 2)); //3

function removeElement(arr, val) {
  // Write a function to remove given element (val) from array and then return array length
}
```

<details><summary><b>Answer</b></summary>

```javascript
function removeElement(arr, val) {
  let k = 0;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] !== val) {
      k++;
    }
  }
  return k;
}
```

</details>

---

### 🟡 45 - Text Encryptor

```javascript
console.log(encryptor("efg", 1, 4)); //abc
console.log(encryptor("XYz", 2, 2)); //Zab

function encryptor(text, orint, k) {
  //Your task is to develop encryption tool to encrypt a given text. Each character should be shifted by k positions to the left or right, indicated by orient. The encryption should wrap around the alphabet, meaning that 'y' becomes 'b' if shifted three positions to the right.
  //🔰 text will consist of letters (both uppercase and lowercase) and spaces only.
  //🔰 orient can have a value of 1, indicating a left shift, or 2, indicating a right shift.
  //🔰 k can be any integer number.
  //🔰Characters should maintain the same case when encrypted, and spaces should not be encrypted.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function encryptor(text, orint, k) {
  //----------- argument validations
  const regex = /^[a-zA-Z\s]+$/;

  for (const letter of text) {
    if (!regex.test(letter)) {
      alert("check text, only letters and spaces are allowed");
      return;
    }
  }

  if (!Number.isInteger(k) || k <= 0) {
    alert("only positive integers are allowed");
    return;
  }

  if (orint !== 1 && orint !== 2) {
    alert("1 indicates to left shift, 2 indicates to right shift");
    return;
  }
  //-------------- correctOverflow()
  function correctOverflow(num) {
    const lowerBound = "a".charCodeAt(); //97
    const upperBound = "z".charCodeAt(); //122

    if (num < lowerBound) {
      return upperBound + 1 - (lowerBound - num);
    } else if (num > upperBound) {
      return lowerBound - 1 + (num - upperBound);
    }

    return num;
  }
  //-----------------------------
  const newK = k % 26;
  let isLeft = orint == 2 ? false : true;

  let ArrayOfLetterInfo = [...text].map((letter) => {
    let obj = {};
    obj.letter = letter;
    obj.charCode = letter.toLowerCase().charCodeAt();
    obj.isUpperCase = letter == letter.toUpperCase() && true;

    if (isLeft) {
      obj.encriptionCode = correctOverflow(obj.charCode - newK);
    } else {
      obj.encriptionCode = correctOverflow(obj.charCode + newK);
    }

    if (obj.charCode == 32) {
      obj.encriptionCode = 32;
    }

    return obj;
  });

  //console.log(ArrayOfLetterInfo);

  let encryptedText = ArrayOfLetterInfo.map((obj) => {
    if (obj.isUpperCase) {
      return String.fromCharCode(obj.encriptionCode).toUpperCase();
    }

    return String.fromCharCode(obj.encriptionCode);
  });

  return encryptedText.join("");
}
```

</details>

---

### 🟢 46 - Same Squares

```javascript
console.log(same([1, 2, 4], [16, 1, 4])); // true
console.log(same([1, 2, 3, 4], [9, 5, 16, 1])); // false

function same() {
  //Write a function such that it accepts two (2) arrays. The intended function should return true if every value in array one has its corresponding value squared in array two.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function same(arr1, arr2) {
  if (arr1.length !== arr2.length) return false;

  let counter1 = {};
  let counter2 = {};

  for (let i = 0; i < arr1.length; i++) {
    let num = arr1[i];
    counter1[num] = (counter1[num] || 0) + 1;
  }
  for (let i = 0; i < arr2.length; i++) {
    let num = arr2[i];
    counter2[num] = (counter2[num] || 0) + 1;
  }

  //console.log(counter1);
  //console.log(counter2);

  for (let key in counter1) {
    if (!(key ** 2 in counter2)) {
      return false;
    }

    if (counter2[key ** 2] !== counter1[key]) {
      return false;
    }
  }

  return true;
}
```

</details>

---

### 🟢 47 - Students List

```javascript
const courses = [
  {
    course: "Mathematics",
    students: [
      { firstName: "John", lastName: "Doe" },
      { firstName: "Jane", lastName: "Smith" },
      { firstName: "Michael", lastName: "Johnson" },
      { firstName: "Emily", lastName: "Davis" },
      { firstName: "William", lastName: "Brown" },
      { firstName: "Sophia", lastName: "Taylor" },
      { firstName: "James", lastName: "Anderson" },
    ],
  },
  {
    course: "History",
    students: [
      { firstName: "Alexander", lastName: "Miller" },
      { firstName: "Olivia", lastName: "Wilson" },
      { firstName: "Isabella", lastName: "Moore" },
      { firstName: "Ethan", lastName: "Martin" },
      { firstName: "Charlotte", lastName: "Lee" },
      { firstName: "Lucas", lastName: "Clark" },
    ],
  },
  {
    course: "Physics",
    students: [
      { firstName: "Liam", lastName: "Hall" },
      { firstName: "Ava", lastName: "Lewis" },
      { firstName: "Noah", lastName: "Walker" },
      { firstName: "Mia", lastName: "Allen" },
      { firstName: "Mason", lastName: "Young" },
      { firstName: "Ella", lastName: "King" },
      { firstName: "Logan", lastName: "Scott" },
    ],
  },
];

console.log(getStudents(courses));

// ["John Doe", "Jane Smith", "Michael Johnson", "Emily Davis", "William Brown", "Sophia Taylor", "James Anderson", "Alexander Miller", "Olivia Wilson", "Isabella Moore", "Ethan Martin", "Charlotte Lee", "Lucas Clark", "Liam Hall", "Ava Lewis", "Noah Walker", "Mia Allen", "Mason Young", "Ella King", "Logan Scott"];

function getStudents(arr) {
  //Write a function that creates array of students with full name
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getStudents(arr) {
  return arr
    .map((mentor) => mentor.students) // Get all students arrays
    .flat() // Flatten into a single array
    .map((student) => `${student.firstName} ${student.lastName}`);
}
```

</details>

---

### 🟢 48 - Spinal Case

```javascript
console.log(spinalCase("Title Case Example")); //title-case-example
console.log(spinalCase("dot.case.example")); //dot-case-example
console.log(spinalCase("SCREAMING_SNAKE_CASE_EXAMPLE")); //screaming-snake-case-example
console.log(spinalCase("snake_case_example")); //snake-case-example
console.log(spinalCase("PascalCaseExample")); //pascal-case-example

function spinalCase(str) {
  //Write a function that transforms various-case string to spinal-case
}
```

<details><summary><b>Answer</b></summary>

```javascript
function spinalCase(str) {
  return (
    str
      // Replace spaces and underscores with a hyphen
      .replace(/\s|_|\./g, "-")
      .replace(/([a-z])([A-Z])/g, "$1-$2")
      .toLowerCase()
  );
}
```

</details>

---
### 🟡 49 - Animal Groups

```javascript
const animals = [
  { name: "Lion", species: "Big Cat" },
  { name: "Tiger", species: "Big Cat" },
  { name: "Elephant", species: "Mammal" },
  { name: "Eagle", species: "Bird" },
  { name: "Shark", species: "Fish" },
  { name: "Falcon", species: "Bird" },
  { name: "Dolphin", species: "Mammal" },
  { name: "Jackal", species: "" },
  { name: "Salmon", species: "" },
];

console.log(groupAnimalsBySpecies(animals));

// {
//     "Big Cat": [
//         {
//             "name": "Lion",
//             "species": "Big Cat"
//         },
//         {
//             "name": "Tiger",
//             "species": "Big Cat"
//         }
//     ],
//     "Mammal": [
//         {
//             "name": "Elephant",
//             "species": "Mammal"
//         },
//         {
//             "name": "Dolphin",
//             "species": "Mammal"
//         }
//     ],
//     "Bird": [
//         {
//             "name": "Eagle",
//             "species": "Bird"
//         },
//         {
//             "name": "Falcon",
//             "species": "Bird"
//         }
//     ],
//     "Fish": [
//         {
//             "name": "Shark",
//             "species": "Fish"
//         }
//     ],
//     "Unknown": [
//         {
//             "name": "Jackal",
//             "species": ""
//         },
//         {
//             "name": "Salmon",
//             "species": ""
//         }
//     ]
// }

function groupAnimalsBySpecies(arr) {
  //You are given an array of animal objects, where each object contains properties such as name (the name of the animal) and species (the species of the animal). Your task is to group these animals by their species using
  //1️⃣ Object.groupBy() method.
  //2️⃣ reduce() method.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function groupAnimalsBySpecies(arr) {
  return Object.groupBy(arr, (animal) => {
    if (animal.species) {
      return animal.species;
    }
    return "Unknown";
  });
}
```
```javascript
function groupAnimalsBySpecies(arr) {
  return arr.reduce((acc, animal) => {
    const species = animal.species || "Unknown";

    if (acc[species]) {
      acc[species].push(animal);
    } else {
      acc[species] = [animal];
    }
    return acc;
  }, {});
}
```

</details>

---

### 🟡 50 - Valid Sudoku

```javascript
const board1 = [
  ['5', '3', '.', '.', '7', '.', '.', '.', '.'],
  ['6', '.', '.', '1', '9', '5', '.', '.', '.'],
  ['.', '9', '8', '.', '.', '.', '.', '6', '.'],
  ['8', '.', '.', '.', '6', '.', '.', '.', '3'],
  ['4', '.', '.', '8', '.', '3', '.', '.', '1'],
  ['7', '.', '.', '.', '2', '.', '.', '.', '6'],
  ['.', '6', '.', '.', '.', '.', '2', '8', '.'],
  ['.', '.', '.', '4', '1', '9', '.', '.', '5'],
  ['.', '.', '.', '.', '8', '.', '.', '.', '9'],
];

const board2 = [
  ['8', '3', '.', '.', '7', '.', '.', '.', '.'],
  ['6', '.', '.', '1', '9', '5', '.', '.', '.'],
  ['.', '9', '8', '.', '.', '.', '.', '6', '.'],
  ['8', '.', '.', '.', '6', '.', '.', '.', '3'],
  ['4', '.', '.', '8', '.', '3', '.', '.', '1'],
  ['7', '.', '.', '.', '2', '.', '.', '.', '6'],
  ['.', '6', '.', '.', '.', '.', '2', '8', '.'],
  ['.', '.', '.', '4', '1', '9', '.', '.', '5'],
  ['.', '.', '.', '.', '8', '.', '.', '7', '9'],
];

function isValidSudoku(board) {
  //Determine if a 9 x 9 Sudoku board is valid. Only the filled cells need to be validated according to the following rules:
  //1️⃣Each row must contain the digits 1-9 without repetition.
  //2️⃣Each column must contain the digits 1-9 without repetition.
  //3️⃣Each of the nine 3 x 3 sub-boxes of the grid must contain the digits 1-9 without repetition.
  //💡 A Sudoku board (partially filled) could be valid but is not necessarily solvable.
  //💡 Only the filled cells need to be validated according to the mentioned rules.//
}
```

<details><summary><b>Answer</b></summary>
add-hoc version
  
```javascript
function isValidSudoku(board) {
  // 🔰 general function to check horizontal-flow of sudoku puzzle
  function Check(board) {
    for (const arr of board) {
      for (const element of arr) {
        if (!isNaN(element * 1) && arr.indexOf(element) != arr.lastIndexOf(element)) {
          return false;
        }
      }
    }
    return true;
  }
  // 🔰 genarate horizontal-flow from grids
  function gridProjection(board) {
    let newBoard = [];

    for (let x = 0; x < 3; x++) {
      let xChunk = x;
      for (let y = 0; y < 3; y++) {
        let yChunk = y;

        let newArr = [];
        for (let i = xChunk * 3; i < 3 * (xChunk + 1); i++) {
          for (let ii = yChunk * 3; ii < 3 * (yChunk + 1); ii++) {
            newArr.push(board[i][ii]);
          }
        }
        newBoard.push(newArr);
      }
    }

    return newBoard;
  }
  // 🔰 genarate horizontal-flow from vertical columns
  function verticalProjection(board) {
    let newBoard = [];

    for (let i = 0; i < 9; i++) {
      let newArr = [];
      for (let ii = 0; ii < 9; ii++) {
        newArr.push(board[ii][i]);
      }
      newBoard.push(newArr);
    }
    return newBoard;
  }

  return Check(board) && Check(verticalProjection(board)) && Check(gridProjection(board));
}
```
AI solution

```javascript
function isValidSudoku(board) {
  const seen = new Set();

  for (let i = 0; i < 9; i++) {
    for (let j = 0; j < 9; j++) {
      const num = board[i][j];
      if (num !== '.') {
        // Create a unique identifier for the current number
        const rowKey = `row${i}-${num}`;
        const colKey = `col${j}-${num}`;
        const boxKey = `box${Math.floor(i / 3)}-${Math.floor(j / 3)}-${num}`;

        // Check if the number has already been seen
        if (seen.has(rowKey) || seen.has(colKey) || seen.has(boxKey)) {
          return false; // Duplicate found
        }

        // Add the current number to the set
        seen.add(rowKey);
        seen.add(colKey);
        seen.add(boxKey);
      }
    }
  }

  return true; // No duplicates found, board is valid
}

```

</details>

---

### 🟡 51 - Knight vs Bishop

```javascript
console.log(knightVsBishop(['c', 4], ['d', 6])); //Knight
console.log(knightVsBishop(['g', 2], ['c', 6])); //Bishop
console.log(knightVsBishop(['f', 2], ['b', 7])); //None

function knightVsBishop(knightPosition, bishopPosition) {
  //You will be provided with two arrays. Each of them contains a string and an integer which represent the positions of the pieces on the chess board: Knight and Bishop.
  //Write a function which returns:
  //🔰 "Knight" if the knight can capture the bishop
  //🔰 "Bishop" if the bishop can capture the knight
  //🔰 "None" if both pieces are safe
}
```

<details><summary><b>Answer</b></summary>
ad-hoc version
  
```javascript
function knightVsBishop(knightPosition, bishopPosition) {
  //generate array of arrays of possible moves of PIECE on COORDINATE
  function possibleMoves(coordinate, piece) {
    let result = [];
    let letters = 'abcdefgh';
    let digits = '12345678';

    for (let i = 0; i < 8; i++) {
      for (let ii = 0; ii < 8; ii++) {
        let temp = [];
        temp[0] = letters[i];
        temp[1] = digits[ii] * 1;

        if (piece == 'knight') {
          if ((coordinate[0] == letters[i + 1] || coordinate[0] == letters[i - 1]) && (coordinate[1] == digits[ii + 2] || coordinate[1] == digits[ii - 2])) {
            result.push(temp);
          }
          if ((coordinate[0] == letters[i + 2] || coordinate[0] == letters[i - 2]) && (coordinate[1] == digits[ii + 1] || coordinate[1] == digits[ii - 1])) {
            result.push(temp);
          }
        }

        if (piece == 'bishop') {
          for (let x = 1; x < 8; x++) {
            if (coordinate[0] == letters[i + x] && coordinate[1] == digits[ii + x]) {
              result.push(temp);
            }
            if (coordinate[0] == letters[i + x] && coordinate[1] == digits[ii - x]) {
              result.push(temp);
            }
            if (coordinate[0] == letters[i - x] && coordinate[1] == digits[ii + x]) {
              result.push(temp);
            }
            if (coordinate[0] == letters[i - x] && coordinate[1] == digits[ii - x]) {
              result.push(temp);
            }
          }
        }
      }
    }
    return result;
  }

  function isArrayInArray(arrayOfArrays, singleArray) {
    return arrayOfArrays.some(arr => JSON.stringify(arr) === JSON.stringify(singleArray));
  }

  const knightMoves = possibleMoves(knightPosition, 'knight');
  if (isArrayInArray(knightMoves, bishopPosition)) return 'Knight';

  const bishopMoves = possibleMoves(bishopPosition, 'bishop');
  if (isArrayInArray(bishopMoves, knightPosition)) return 'Bishop';

  return 'None';
}
```
AI version

```javascript
function knightVsBishop(np, bp) {
  np[0] = np[0].charCodeAt(0);
  bp[0] = bp[0].charCodeAt(0);

  let diffx = Math.abs(np[1] - bp[1]);
  let diffy = Math.abs(np[0] - bp[0]);

  if (diffx == diffy) {
    return 'Bishop';
  }

  if ((diffx == 2 && diffy == 1) || (diffx == 1 && diffy == 2)) {
    return 'Knight';
  }

  return 'None';
}
```

</details>

---

### 🟢 52 - Update Object Value

```javascript
let shoppingList = [
  { name: 'apples', quantity: 5 },
  { name: 'bananas', quantity: 2 },
  { name: 'carrots', quantity: 7 },
  { name: 'detergent', quantity: 1 },
];

console.log(updateQuantity(shoppingList, 'bananas', 99));

// [
//   { name: 'apples', quantity: 5 },
//   { name: 'bananas', quantity: 99 },
//   { name: 'carrots', quantity: 7 },
//   { name: 'detergent', quantity: 1 },
// ];

function updateQuantity(arr, itemName, newQuantity) {
  //Find the given item in the array of objects and update its quantity to given quantity. Return the updated shopping list as a new array without mutating the original array.
  //🔰 try to use .with method
}
```

<details><summary><b>Answer</b></summary>

```javascript
function updateQuantity(arr, itemName, newQuantity) {
  return arr.map(e => {
    if (e.name === itemName) {
      e.quantity = newQuantity;
    }
    return e;
  });
}
```
.with method

```javascript
function updateQuantity(arr, itemName, newQuantity) {
  // Find the index of the item with the given name
  const index = arr.findIndex(item => item.name === itemName);

  // If the item is not found, return the original list
  if (index === -1) return arr;

  // Create a new object with the updated quantity
  const updatedItem = { ...arr[index], quantity: newQuantity };

  // Use the `with()` method to create a new array with the updated item
  return arr.with(index, updatedItem);
}
```

</details>

---

### 🟢 - Find Single

```javascript
const couples = [10, 5, 10, 5, 12];
console.log(findSingle(couples)); //12

function findSingle(arr) {
  //All but one of the entries in this array are represented twice. Write the function to detect single entry
}
```

<details><summary><b>Answer</b></summary>

```javascript
function findSingle(arr) {
  return arr.reduce((acc, cur) => {
    if (arr.lastIndexOf(cur) == arr.indexOf(cur)) {
      acc += cur;
    }
    return acc;
  }, 0);
}
```
with algorithm

```javascript
function findSingle(arr) {
  let numCount = {};

  // Count occurrences of each number
  for (let num of arr) {
    numCount[num] = (numCount[num] || 0) + 1;
  }

  // Find the number with a count of 1
  for (let num in numCount) {
    if (numCount[num] === 1) {
      return parseInt(num); // Return the single number
    }
  }
}
```

</details>

---

<!--

### 🟢🔴🟡

```javascript

```

<details><summary><b>Answer</b></summary>

```javascript

```

</details>

---

-->
