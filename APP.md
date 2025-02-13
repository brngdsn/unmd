```
// .gitignore
node_modules/
.env


```

```
// .nvmrc
v20.8.0


```

```json
// package.json
{
  "name": "@brngdsn/unmd",
  "version": "0.2.0",
  "description": "A CLI tool to unpack code fences from Markdown into files.",
  "type": "module",
  "bin": {
    "unmd": "./bin/unmd.js"
  },
  "scripts": {
    "start": "node ./bin/unmd.js"
  },
  "keywords": [
    "markdown",
    "extract",
    "code-fence",
    "unmarkdown"
  ],
  "author": "brn.gdsn@gmail.com",
  "license": "MIT",
  "dependencies": {
    "markdown-it": "^13.0.1"
  }
}


```

```js
// bin/unmd.js
#!/usr/bin/env node

import { readFile, writeFile, mkdir } from 'node:fs/promises';
import path from 'node:path';
import process from 'node:process';
import MarkdownIt from 'markdown-it';

async function main() {
  const [,, ...args] = process.argv;

  if (args.length < 1) {
    console.error("Usage: unmd <markdown-file>");
    process.exit(1);
  }

  const markdownFile = args[0];

  let mdContent;
  try {
    mdContent = await readFile(markdownFile, 'utf8');
  } catch (err) {
    console.error(`Error reading file "${markdownFile}": ${err.message}`);
    process.exit(1);
  }

  const mdParser = new MarkdownIt();
  const tokens = mdParser.parse(mdContent, {});

  for (const token of tokens) {
    // We're only interested in fenced code blocks
    if (token.type === 'fence') {
      const fenceContent = token.content.trimEnd();

      // Split by new lines
      const lines = fenceContent.split('\n');
      if (lines.length === 0) continue;

      // We expect the first line to contain the file path in a comment, e.g. "// src/index.js"
      const firstLine = lines[0].trim();
      if (!firstLine.startsWith('// ')) continue;

      // Extract the file path from that comment
      const filePath = firstLine.replace('// ', '').trim();

      // The rest of the lines after the first line is our actual code
      const code = lines.slice(1).join('\n');

      try {
        const fullPath = path.join(process.cwd(), filePath);
        await mkdir(path.dirname(fullPath), { recursive: true });
        await writeFile(fullPath, code, 'utf8');
        console.log(`Created file: ${fullPath}`);
      } catch (err) {
        console.error(`Error writing file "${filePath}": ${err.message}`);
      }
    }
  }
}

try {
  // Top-level await is allowed in ES2024 / Node.js v20.8.0 with "type":"module"
  await main();
} catch (err) {
  console.error(err);
  process.exit(1);
}


```
