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
function buildRightAligned(n) {
  let node = "";
  for (let i = 0; i < n; i++) {
    node += "#";
    console.log(node);
  }
}

function buildLeftAligned(n) {
  for (let i = 1; i <= n; i++) {
    let node = "";
    for (let ii = 1; ii <= n - i; ii++) {
      node += " ";
    }

    for (let ii = 1; ii <= i; ii++) {
      node += "#";
    }
    console.log(node);
  }
}

function buildPyramid(n) {
  for (let i = 1; i <= n; i++) {
    let node = "";
    for (let ii = 1; ii <= n - i; ii++) {
      node += " ";
    }

    for (let ii = 1; ii <= i; ii++) {
      node += "#";
    }

    for (let ii = 1; ii <= i; ii++) {
      node += "#";
    }
    console.log(node);
  }
}
```

</details>

### 🟢 03 - Mode

```javascript
const arr = [3, "a", "a", "a", 2, 3, "a", 3, "a", 2, 4, 9, 3];
console.log(getMode(arr)); //a - 5 times

function getMode(array) {
  //Write a function to find the most frequent item of an array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function getMode(array) {
  let set1 = new Set(array);
  let uniqArr = [...set1]; // [3, 'a', 2, 4, 9]

  let countArr = [];
  for (let i = 0; i < uniqArr.length; i++) {
    let counter = 0;
    for (let e = 0; e < arr.length; e++) {
      if (uniqArr[i] == arr[e]) {
        counter++;
      }
    }
    countArr.push(counter); // [4, 5, 2, 1, 1]
  }

  let maxNum = Math.max(...countArr); //5
  let placeNum = countArr.findIndex((e) => e == maxNum); //1

  return `${uniqArr[placeNum]} - ${maxNum} times`;
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
  const array = [...string];
  const newArray = Array.from(array, (e) => {
    return e == e.toUpperCase() ? e.toLowerCase() : e.toUpperCase();
  });
  return newArray.join("");
}
```

</details>

---

### 🟢 05 - iDuplicate

```javascript
const cars = ["bmw", "opel", "lada", "opel", "BMW"];
console.log(dublicateRemover(cars)); // ['bmw', 'opel', 'lada']

function dublicateRemover(array) {
  //Write a function to remove duplicate items from array (case insensitivity) using/not using set
}
```

<details><summary><b>Answer</b></summary>

```javascript
function dublicateRemover(array) {
  let newarray = array.map((e) => {
    return e.toLowerCase();
  });
  let dupChars = newarray.filter((c, index) => {
    return newarray.indexOf(c) === index;
  });

  return dupChars;
}

function dublicateRemover(array) {
  const mySet = new Set();
  for (let elem of array) {
    mySet.add(elem.toLowerCase());
  }
  return [...mySet];
}
```

</details>

---

### 🟢 06 - Dublicate Finder

```javascript
const nums = [1, 2, -2, 4, 5, 4, 7, 8, 7, 7];
console.log(dublicateFinder(nums)); //["4", "7"];

function dublicateFinder(arr) {
  //Write a function to get array of duplicate values in array.
}
```

<details><summary><b>Answer</b></summary>

```javascript
function dublicateFinder(arr) {
  let result = arr.filter((e, index) => {
    return arr.indexOf(e) !== index;
  });
  return [...new Set(result)];
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
const word1 = "listen";
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

<!--

### 🟢

```javascript

```

<details><summary><b>Answer</b></summary>

```javascript

```

</details>

---

-->
