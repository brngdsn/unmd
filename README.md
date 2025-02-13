# unmd

**unmd** is a command-line tool that extracts code blocks from Markdown files and writes them to their respective files. This is especially useful for projects where you want to maintain code examples or templates in Markdown documentation and later convert them into standalone files.

---

## Features

- **Automatic File Creation:** Extracts code fences from Markdown and writes them to files based on a path specified in the code block.
- **Directory Support:** Automatically creates directories if they do not exist.
- **Simple CLI Usage:** Run the tool with a single command and a Markdown file.

---

## Installation

### Prerequisites

- **Node.js:** Make sure you have [Node.js](https://nodejs.org/) version **20.8.0** or later. You can manage Node.js versions using [nvm](https://github.com/nvm-sh/nvm) (the `.nvmrc` file is included in this repository).

### Install Globally

You can install **unmd** globally using npm:

```bash
npm install -g @brngdsn/unmd
```

This will make the `unmd` command available globally on your system.

---

## Usage

Run **unmd** from the command line with the path to your Markdown file:

```bash
unmd <markdown-file>
```

### How It Works

1. **Code Fence Parsing:** The tool parses your Markdown file for fenced code blocks.
2. **File Path Declaration:** It expects the first line of each code block to be a comment declaring the file path (e.g., `// src/index.js`).
3. **File Creation:** The remaining lines in the code block are treated as the file's content. The tool creates the file (and any necessary directories) and writes the content to it.

---

## Example

Given a Markdown file `example.md` with the following content:

```markdown
# Example

Here is a simple JavaScript file:

```js
// src/index.js
console.log("Hello, world!");
```
```

Running the command:

```bash
unmd example.md
```

Will create the file `src/index.js` with the following content:

```js
console.log("Hello, world!");
```

---

## Contributing

Contributions are welcome! Please fork the repository and submit pull requests for any features or bug fixes.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contact

For questions or feedback, please contact [brn.gdsn@gmail.com](mailto:brn.gdsn@gmail.com).

Happy coding!
