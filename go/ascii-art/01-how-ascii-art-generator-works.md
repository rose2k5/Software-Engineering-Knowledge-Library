# How Does an ASCII Art Generator Actually Work? Build One in Go from Scratch

Before writing any Go code, it's worth understanding what an ASCII Art generator is actually doing behind the scenes. Once you understand the workflow, the implementation becomes much easier to follow.

## What Is ASCII Art?

ASCII Art is a way of creating images and decorative text using ordinary keyboard characters instead of pixels. By arranging characters such as `_`, `|`, `/`, `\`, and `*` in specific patterns, it's possible to create letters, logos, and even simple illustrations.

For example, the cat below is made entirely from text:

```text
 /\_/\\
( o.o )
 > ^ <
```

Although it looks like a picture, every part of it is just a keyboard character placed in the right position.

## How Does an ASCII Art Generator Work?

An ASCII Art generator doesn't create or draw letters. Instead, it replaces each character you type with a predefined text pattern.

Suppose the user enters:

```text
GO
```

The program processes the input in four steps:

1. Read each character from the user's input.
2. Find the matching ASCII pattern for every character.
3. Join those patterns together row by row.
4. Print the completed ASCII Art to the terminal or browser.

Whether the generator is written in Go, Python, or Java, the overall idea remains the same.

## Where Are the Character Patterns Stored?

The predefined patterns are stored in a **banner file**. Think of it as a collection of templates where every printable character has its own ASCII representation.

A simplified example looks like this:

```text
A → ASCII pattern
B → ASCII pattern
C → ASCII pattern
```

When the program reads the letter `A`, it retrieves the pattern for `A`. It repeats the same process for every other character until the entire input has been processed.

In the next article, we'll open a banner file and explore how it's organized.

## Why Are Characters Printed Row by Row?

Each character pattern contains multiple rows. In this project, every character in the standard banner is **8 rows high**.

If the input is:

```text
HI
```

the program doesn't print the complete pattern for `H` and then the complete pattern for `I`. Doing so would stack the letters vertically.

Instead, it prints one row from each character at a time.

```text
Row 1 of H + Row 1 of I
Row 2 of H + Row 2 of I
Row 3 of H + Row 3 of I
...
Row 8 of H + Row 8 of I
```

By combining the rows in this way, the letters appear side by side, forming a single word instead of separate blocks of text.

## The Complete Workflow

Every ASCII Art generator follows the same basic process:

```text
User Input
     │
     ▼
Read each character
     │
     ▼
Find the matching pattern
     │
     ▼
Combine the rows
     │
     ▼
Display the final ASCII Art
```

Although the output looks like an image, the program is simply reading text, retrieving patterns, arranging them, and displaying the result.

## Why Is This Project Worth Building?

An ASCII Art generator is more than a fun programming exercise. It introduces several concepts that are common in software engineering, including:

* Reading data from files.
* Processing user input.
* Working with strings and runes.
* Designing simple algorithms.
* Handling invalid input.
* Structuring a Go application.

More importantly, it teaches you how software transforms one form of data into another—a concept you'll encounter in many real-world applications.

## Key Takeaways

After reading this article, you should understand that:

* ASCII Art is created using ordinary keyboard characters.
* Every printable character has a predefined pattern.
* Those patterns are stored in a banner file.
* Characters are rendered one row at a time to keep words aligned correctly.
* Understanding this workflow makes the Go implementation much easier to follow.

## What's Next?

Now that you understand the overall workflow, the next step is to look inside the banner file itself.

In the next article, **Inside Banner Files: The Hidden Engine Behind ASCII Art**, we'll explore how banner files are structured, why they contain exactly 95 printable ASCII characters, and how the program locates the correct pattern for every letter.

