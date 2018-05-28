# prompt-confirm [![NPM version](https://img.shields.io/npm/v/prompt-confirm.svg?style=flat)](https://www.npmjs.com/package/prompt-confirm) [![NPM monthly downloads](https://img.shields.io/npm/dm/prompt-confirm.svg?style=flat)](https://npmjs.org/package/prompt-confirm) [![NPM total downloads](https://img.shields.io/npm/dt/prompt-confirm.svg?style=flat)](https://npmjs.org/package/prompt-confirm) [![Linux Build Status](https://img.shields.io/travis/enquirer/prompt-confirm.svg?style=flat&label=Travis)](https://travis-ci.org/enquirer/prompt-confirm) [![Windows Build Status](https://img.shields.io/appveyor/ci/enquirer/prompt-confirm.svg?style=flat&label=AppVeyor)](https://ci.appveyor.com/project/enquirer/prompt-confirm)

> Confirm (yes/no) prompt. Can be used standalone or with a prompt system like [Enquirer](http://enquirer.io).

Please consider following this project's author, [Jon Schlinkert](https://github.com/jonschlinkert), and consider starring the project to show your :heart: and support.

![prompt-confirm example](https://raw.githubusercontent.com/enquirer/prompt-confirm/master/docs/example.gif)

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save prompt-confirm
```

## Usage

**Question**

Pass a string or question object to the constructor:

```js
const Confirm = require('prompt-confirm');
const prompt = new Confirm('Do you like chocolate?');

// or
const prompt = new Confirm({
  name: 'chocolate', 
  message: 'Do you like chocolate?'
});
```

**Run the prompt**

You can use one of the following two methods for running the prompt:

```js
// async
prompt.ask(function(answer) {
  console.log(answer);
});

// or promise
prompt.run()
  .then(function(answer) {
    console.log(answer);
  });
```

**Examples**

```js
const confirm = new Confirm('Like chocolate?')
  .ask(function(answer) {
    console.log(answer);
  });

const confirm = new Confirm('Like chocolate?')
  .run()
  .then(function(answer) {
    console.log(answer);
  });
```

## Usage with [enquirer](http://enquirer.io)

```js
const Enquirer = require('enquirer');
const enquirer = new Enquirer();

enquirer.register('confirm', require('prompt-confirm'));
```

### Enquirer example

[Enquirer](http://enquirer.io) supports either the declarative object-oriented (inquirer-style) question format or a more expressive format using the `.question` method.

**Declarative**

Inquirer-style declarative format (takes an array or object):

```js
const questions = [
  {
    type: 'confirm',
    name: 'chocolate',
    message: 'Like chocolate?'
  },
  {
    type: 'confirm',
    name: 'vanilla',
    message: 'Like vanilla?'
  }
];

enquirer.ask(questions)
  .then(function(answers) {
    console.log(answers)
  });
```

**Expressive**

Pre-define questions and easily compose prompts by passing the name(s) of the prompts to run:

```js
enquirer.question('chocolate', 'Like chocolate?', {type: 'confirm'});
enquirer.question('vanilla', 'Like vanilla?', {type: 'confirm'});

enquirer
  .prompt(['chocolate', 'vanilla'])
  .then(function(answers) {
    console.log(answers)
  });
```

## About

<details>
<summary><strong>Contributing</strong></summary>

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

</details>

<details>
<summary><strong>Running Tests</strong></summary>

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

</details>

<details>
<summary><strong>Building docs</strong></summary>

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

</details>

### Related projects

You might also be interested in these projects:

* [enquirer-prompt](https://www.npmjs.com/package/enquirer-prompt): Base prompt module used for creating custom prompt types for Enquirer. | [homepage](https://github.com/jonschlinkert/enquirer-prompt "Base prompt module used for creating custom prompt types for Enquirer.")
* [enquirer](https://www.npmjs.com/package/enquirer): Intuitive, plugin-based prompt system for node.js. | [homepage](http://enquirer.io "Intuitive, plugin-based prompt system for node.js.")
* [prompt-checkbox](https://www.npmjs.com/package/prompt-checkbox): Multiple-choice/checkbox prompt. Can be used standalone or with a prompt system like [Enquirer](http://enquirer.io). | [homepage](https://github.com/enquirer/prompt-checkbox "Multiple-choice/checkbox prompt. Can be used standalone or with a prompt system like [Enquirer].")
* [prompt-radio](https://www.npmjs.com/package/prompt-radio): Radio prompt. Can be used as a standalone prompt, or as a plugin for [Enquirer](http://enquirer.io). | [homepage](https://github.com/enquirer/prompt-radio "Radio prompt. Can be used as a standalone prompt, or as a plugin for [Enquirer].")

### Contributors

| **Commits** | **Contributor** | 
| --- | --- |
| 39 | [jonschlinkert](https://github.com/jonschlinkert) |
| 9 | [doowb](https://github.com/doowb) |

### Author

**Jon Schlinkert**

* [LinkedIn Profile](https://linkedin.com/in/jonschlinkert)
* [GitHub Profile](https://github.com/jonschlinkert)
* [Twitter Profile](https://twitter.com/jonschlinkert)

### License

Copyright © 2018, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.6.0, on May 28, 2018._