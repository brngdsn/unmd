# unmd

**unmd** is a CLI tool that extracts code fences from Markdown files and writes them to disk as files. It is especially useful when working with AI chats that generate code or entire projects in Markdown format.

---

## Features

- **Extract Code Fences:** Scans Markdown files for fenced code blocks.
- **File Path Detection:** Expects the first line of each code block to be a comment specifying the target file path (e.g., `// src/index.js`).
- **Automatic Directory Creation:** Creates necessary directories if they don't already exist.
- **Seamless Integration:** Perfect for processing Markdown outputs from AI code generators.

---

## Requirements

- **Node.js:** v20.8.0 or later (see [`.nvmrc`](./.nvmrc))
- **npm:** Comes with Node.js

---

## Installation

Install **unmd** globally using npm:

```bash
npm install -g @brngdsn/unmd
```

Alternatively, you can run it directly using [npx](https://www.npmjs.com/package/npx):

```bash
npx @brngdsn/unmd <markdown-file>
```

---

## Usage

The CLI accepts a Markdown file as an argument and processes all code fences with a file path comment on the first line.

### Markdown File Format

Each code fence should start with a comment that specifies the file path, followed by the code. For example:

```markdown
# My Project

Here is an example of how to define a file within Markdown:

```js
// src/index.js
console.log("Hello, world!");
```
```

When you run **unmd** on the above Markdown, it will create a file at `src/index.js` containing:

```js
console.log("Hello, world!");
```

### Running the Tool

Simply pass the Markdown file as an argument:

```bash
unmd README.md
```

If no file is provided, the tool will display a usage message:

```bash
Usage: unmd <markdown-file>
```

---

## How It Works

1. **Read File:** The tool reads the specified Markdown file.
2. **Parse Markdown:** It uses [markdown-it](https://github.com/markdown-it/markdown-it) to parse the Markdown content.
3. **Extract Code Fences:** It scans for fenced code blocks.
4. **Detect File Path:** It looks for a file path in the first line of each code block (formatted as `// path/to/file.ext`).
5. **Write Files:** It writes the remaining lines of the code block to the corresponding file, creating directories as needed.

---

## Contributing

Contributions, bug reports, and feature requests are welcome! Please open an issue or submit a pull request on the [GitHub repository](https://github.com/your-repo).

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Author

brn.gdsn@gmail.com

Happy coding!