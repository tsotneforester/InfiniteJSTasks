<div align="center">
  <img height="260" src="https://github.com/tsotneforester/infiniteJSTasks/assets/79293287/1cc7c4f6-0317-4e86-bead-11b50bc8cd97">

  <h1>🔰︱𝗶̲̅𝗻̲̅𝗳̲̅𝗶̲̅𝗻̲̅𝗶̲̅𝘁̲̅𝗲̲̅𝗝̲̅𝗦̲̅︱🔰 🚦︱🆃🅰🆂🅺🆂</h1>
</div>

<p>

[InfiniteJS](https://gpx.ge/infiniteJS/) has been developing in parallel with my web developer career. It was conceived as a more understandable alternative to our dear [Eloquent JavaScript](https://eloquentjavascript.net/), well... for beginners at least. Actually, it turned out to resembled a detective's notebook: practical for inner usage and bit abstract for outer glance. It went beyond JavaScript and covered almost every aspect I encountered in my career growth.

The origin of the tasks is very diverse: I had to thank [CS50](https://pll.harvard.edu/course/cs50-introduction-computer-science) for some of them, I encountered some in practice, and some... I tried to offer interesting and wonderful tasks. 👴🏻 We are starting to enjoy our own little successes! 🧲 🧁 ⚱️

</p>

> [!NOTE]  
> This repo was created in 2024, the tasks provided here are not based on the JavaScript syntax and behavior only, but any other languages can possibly handle them. Since JavaScript is my native programming language and most preferable one and since it as well as my knowledge has been constantly evolving, there are newer language features, newer and better solutions to problems here.

![Discord](https://img.shields.io/discord/1027831568745648198)

###### 1. What's the output?

```javascript
function sayHi() {
  console.log(name);
  console.log(age);
  var name = "Lydia";
  let age = 21;
}

sayHi();
```

- A: `Lydia` and `undefined`
- B: `Lydia` and `ReferenceError`
- C: `ReferenceError` and `21`
- D: `undefined` and `ReferenceError`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

Within the function, we first declare the `name` variable with the `var` keyword. This means that the variable gets hoisted (memory space is set up during the creation phase) with the default value of `undefined`, until we actually get to the line where we define the variable. We haven't defined the variable yet on the line where we try to log the `name` variable, so it still holds the value of `undefined`.

Variables with the `let` keyword (and `const`) are hoisted, but unlike `var`, don't get <i>initialized</i>. They are not accessible before the line we declare (initialize) them. This is called the "temporal dead zone". When we try to access the variables before they are declared, JavaScript throws a `ReferenceError`.

</p>
</details>

---
