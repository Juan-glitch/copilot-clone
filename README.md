![Captain Stack](./logo.svg)

# Captain Stack — Code suggestion for VSCode


This feature is somewhat similar to [Github Copilot](https://copilot.github.com/)'s code suggestion. But instead of using AI, it sends your search query to Google, then retrieves StackOverflow answers and autocompletes them for you. Have question? [Join our Discord server](https://discord.gg/5F5tDsWFmp) [![Discord Chat](https://img.shields.io/discord/864164585070526475.svg)](https://discord.gg/5F5tDsWFmp)  

_Captain Stack is launched on Product Hunt and would appricate your support_

<a href="https://www.producthunt.com/posts/captain-stack?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-captain-stack" target="_blank"><img src="https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=302437&theme=light" alt="Captain Stack - An open source alternative to GitHub Copilot | Product Hunt" style="width: 250px; height: 54px;" width="250" height="54" /></a> 


![Demo Video](./demo.gif)

## Table of contents:

1. [Installation](#1-installation)
2. [Play with Captain Stack](#2-play-with-captain-stack)
3. [Notes](#3-notes)
4. [Changelog](#4-changelog)


_Note: ⚠️ This extension uses a proposed API (inline-completion) and can only be used for extension development in [VSCode Insider release](https://code.visualstudio.com/insiders/). It's not yet available on VSCode_

---

## 1. Installation

**Check out the installation video: https://youtu.be/MD-kzsF0Scg**

Before installation, make sure you have [VSCode Insider](https://code.visualstudio.com/insiders/). You'll be using this version. To install and starting Captain Stack:

1. Download this repository to your local machine. Unzip and open it on VSCode Insider (make sure the root directory is the same as `package.json` file)
2. (optional) Run `npm install` in the terminal to install dependencies. _A `postinstall` script would download the latest version of `vscode.proposed.d.ts`_
3. Run the `Run Extension` target in the Debug View. Or from the top menu, choose `Run > Start Debugging`.

This will:
- Start a task `npm: watch` to compile the code and watch for changes
- Open a new VSCode windows (you should play the extension here)

_Note: when you make changes, you should refresh that windows to apply changes. To refersh, open Command Palette (Command+Shift+P on MacOS, or Ctrl+Shift+P on Windows), then choose "Developer: Reload window"_

---

## 2. Play with Captain Stack

To trigger inline completion, you'll need to type `//find {your keyword}.` (start with `//find`, end with a dot `.`)

For example
```js
//find binary search in javascript.
```

Make sure that `showInlineCompletions` is enabled in your settings!
```
"editor.inlineSuggest.enabled": true
```

---

## 3. Notes

- There are more code sources that should be considered besides StackOverflow
- If you see `unsupported` error message, ignore it

**Limits:**
- The extension use fetch-node to get page content, and I don't know if there is any fetching limit
- The extension uses querySelector to extract code and other info. There is a risk when either StackOverflow or Google changing its querySelector

If those factor became problems, the extension could be using their official APIs instead.



## 4. Changelog

- Jul 01, 2021 - Added snippet source (thanks for [mechero's suggestion](https://news.ycombinator.com/item?id=27698687))
- Jun 30, 2021 — Publish the initial version

**Feel free to open a thread for feedback or discussion. And have fun!**