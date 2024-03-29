<img align="center" src="https://github.com/coterahq/nasty-assets/blob/main/logo.svg?raw=true" alt="Get ERA Docs" style="width:100%;height:100px"/></a><br/><br/>
<p align="center">ERA is a practical framework for building composable data applications that are easy to maintain. Think type safety, beautiful abstractions, unit tests... everything an engineer expects in 2024.</p>

<sub>By [Cotera](https://cotera.co), inspired by [Ruby Koans](https://www.rubykoans.com/).</sub>

## 👋 Learn ERA By Example

A simple repository to get you started with understanding the ERA Analytics Toolkit, quickly.

## 💡 Who is this for? 

This is for people who have a little understanding of SQL but maybe not
familiarity with Typescript, unit tests, or advanced SQL constructs (windows,
aggregates, ...etc). After teaching the basics, the examples get progressively
more advanced and show of more powerful analytics tools.

Each example is run via unit tests, as a way to demonstrate the power you can leverage when you bring tests to your analytics code.

## ⚡️ Quickstart
Make sure you have NodeJS installed ([Download](https://nodejs.org/en/downloaddownload)).

:warning: **Installation can take a few minutes, due to downloading the duckdb binary**

```bash
$ git clone https://github.com/coterahq/learn-era-by-example.git

$ cd learn-era-by-example

$ npm i

$ npm run test
```
If this is all setup correctly, you should see an output similar to this:
<img align="center" alt="Era test example" src="https://github.com/coterahq/nasty-assets/blob/main/learn-nasty-test_01.png?raw=true"/>

### :heavy_check_mark: Running tests

All tests

```bash
$ npm run test
```

Running a single test

```bash
# npm run test -- <file name>
$ npm run test -- src/01_the-basics.test.ts
```

Running `.learn.ts` files

```bash
$ TEST_LEARN=true npm test
```
## The First Example

Open `src/01_the-basics.test.ts` in your test editor and locate the test titled "learn to complete an example".

This test is **broken** by default, and contains a comment showing you how to fix it.

Edit the test to look something like so:
```typescript
test("learn to complete an example", async () => {
  const query = Values(data).select((t) => {
    return {
      a: t.attr('a'),
      b: t.attr('b')
    }
  });

  expect(await query.execute(db())).toEqual([
    { a: 1, b: "Foo" },
    { a: 2, b: "Bar" },
    { a: 3, b: "Baz" },
  ]);
});
```

When you re-run the test command, it should now pass. :fireworks:
```bash
$ npm run test -- src/01_the-basics.test.ts
```

## ⚽ Goals 

By the end, you should have a reasonable understanding of how to use [ERA](https://getera.com) to perform analytics tasks on some example data.

### :eyes: But How?

Through test driven development! 🚦

In the practice of test-driven development, the guiding principle is often summarized as "red, green, refactor." This means first creating a test that fails upon execution (indicated by red), then adjusting the code until the test succeeds (signified by green), and finally examining and improving the code's structure or clarity (refactoring).

For these examples, you will need to run the test and see it fail (red), make the test pass (green), then take a moment and reflect upon the test to see what it is teaching you and improve the code to better communicate its intent (refactor).

Normally the flow looks like this:

```mermaid
graph LR
    A[Run Test] --> B{Did It Fail?}
    B -->|yes| D[Edit]
    B -->|No| C{Needs Refactor?}
    D --> A
    C -->|Yes| D
    C -->|No| E[Next Example :arrow_forward:]
```


## :open_file_folder: How is this structured

### The `.learn.ts` files

Each `.learn.ts` file contains examples of how to use the concept in ERA. Start in these files to see examples on how to use a concept.

### The `.test.ts` files

These let you apply the skills you've learned in examples by fixing unit tests.

```typescript
test.skip("I'm a description of the example", () => {
  // Example code here
});
```

In order to attempt an example remove the `.skip` like so

```typescript
test("I'm a description of the example", () => {
  // Example code here
});
```

## 🎯 Troubleshooting

### Make sure NodeJS is installed

```bash
$ node --version
```

If NodeJS is installed, you should see an output like 

```
v18.17.0
```

### Are your dependencies up to date?

Try running this to update your dependencies.
```bash
$ npm i
```

### Still Having issues?
Join our [Discord](https://discord.com/channels/1215021133003235360/1215021133594890252) and get in touch!

### Didn't this used to be called "NASTY"?

It did! That was our internal name, but we renamed it based on community feedback
