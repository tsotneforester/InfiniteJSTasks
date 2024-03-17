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
> This repo was created in 2024, the tasks provided here are not based on the JavaScript syntax and behavior only, but any other languages can possibly handle them. Since JavaScript is my native programming language and most preferable one and since it as well as my knowledge has been constantly evolving, there are newer language features, newer and better solutions to problems here.

Please join my discord channel

[![Discord](https://img.shields.io/discord/1027831568745648198?style=for-the-badge&logo=discord&logoColor=white&label=Discord&labelColor=%235865F2)](https://discord.gg/FMTkTe7q)

> blockquote

| Feel free to use them in a project! 😃 I would _really_ appreciate a reference to this repo, I create the questions and explanations (yes I'm sad lol) and the community helps me so much to maintain and improve it! 💪🏼 Thank you and have fun! |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |

:octocat: :rabbit: :alien: :+1: :bee: :bell: :ghost: :bulb: :imp:

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].

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
