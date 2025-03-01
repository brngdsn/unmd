<div align="center">
<h1 align="center">
<img src="https://raw.githubusercontent.com/PKief/vscode-material-icon-theme/ec559a9f6bfd399b82bb44393651661b08aaf7ba/icons/folder-markdown-open.svg" width="100" />
<br>UNMD</h1>
<h3>◦ A CLI tool to unpack code fences from Markdown into files.</h3>
<h3>◦ Developed with modern JavaScript technologies.</h3>

<p align="center">
<img src="https://img.shields.io/badge/license-MIT-5D6D7E.svg" alt="License" />
<img src="https://img.shields.io/github/last-commit/brngdsn/unmd?style=flat-square&color=5D6D7E" alt="Last Commit" />
<img src="https://img.shields.io/github/languages/top/brngdsn/unmd?style=flat-square&color=5D6D7E" alt="Top Language" />
<img src="https://img.shields.io/github/languages/count/brngdsn/unmd?style=flat-square&color=5D6D7E" alt="Language Count" />
<img src="https://img.shields.io/github/repo-size/brngdsn/unmd?style=flat-square&color=5D6D7E" alt="Repo Size" />
</p>
<p align="center">
<img src="https://img.shields.io/badge/Node.js-8CC84B.svg?style=flat-square&logo=Node.js&logoColor=white" alt="Node.js" />
<img src="https://img.shields.io/badge/Markdown-it-000000.svg?style=flat-square&logo=Markdown-It&logoColor=white" alt="Markdown-it" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E.svg?style=flat-square&logo=JavaScript&logoColor=black" alt="JavaScript" />
</p>
</div>

---

## 📖 About the Project
`unmd` is a command-line interface (CLI) tool designed to extract code fences from Markdown files and create the corresponding files on the filesystem. This tool is particularly useful for developers who want to manage code snippets, documentation, or any content stored within Markdown that include executable code blocks.

## 🎯 Features
- Extracts code blocks annotated with file paths from Markdown files.
- Automatically creates corresponding files in the specified structure.
- Simple and effective command-line usage.

## 🚀 Quick Start
1. **Clone the repository**:
   ```bash
   git clone https://github.com/brngdsn/unmd.git
   cd unmd
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the tool**:
   ```bash
   npx unmd path/to/your/markdown-file.md
   ```

4. Optionally, you can create an alias for easier usage:
   ```bash
   alias unmd="node ./bin/unmd.js"
   ```

## 🛠️ Tech Stack
- **Node.js**: JavaScript runtime to execute the CLI tool.
- **Markdown-it**: A Markdown parser used for interpreting the Markdown content.

## 📂 Folder Structure
```plaintext
.
├── bin
│   └── unmd.js         # Main CLI executable script
├── .gitignore          # Git ignore file
├── .nvmrc              # Node version manager configuration
└── package.json        # Node package configuration
```

## 📜 License & Credits
This project is licensed under the MIT License. For detailed information, please refer to the [LICENSE](LICENSE) file.

Contributions are welcome! Please submit issues or pull requests for enhancements and bug fixes, and I will be glad to review them.

---

For further queries, feel free to reach out at [brn.gdsn@gmail.com](mailto:brn.gdsn@gmail.com) or open issues in the GitHub repository. Happy coding!