# Publishing Your VS Code Extension

This guide walks you through packaging and publishing your VS Code extension using `@vscode/vsce`.

---

## Prerequisites

1. **Node.js and npm** must be installed.
2. You must have a **Microsoft account**.
3. You must have a **Personal Access Token (PAT)** from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/manage).

---

## Step 1: Install `vsce`

```bash
npm install -g @vscode/vsce
```

---

## Step 2: Package the Extension

Make sure your extension has the following files configured:

* `package.json` with the following fields:

  * `name`
  * `displayName`
  * `description`
  * `version`
  * `publisher`
  * `engines.vscode`
  * `categories`
* Compiled source code, e.g., `out/main.js`

Then run:

```bash
vsce package
```

This will generate a `.vsix` file:

```
layout-saver-1.0.0.vsix
```

### Example Output

```
Files included in the VSIX:
layout-saver-1.0.0.vsix
├─ [Content_Types].xml
├─ extension.vsixmanifest
└─ extension/
   ├─ LICENSE.txt [0.65 KB]
   ├─ package.json [1.81 KB]
   ├─ readme.md
   └─ out/
      ├─ main.js [2.66 KB]
      └─ main.js.map [6 KB]
```

---

## Step 3: Publish the Extension

### 3.1 Create a Publisher (first time only)

```bash
vsce create-publisher <publisher-name>
```

This will prompt you to sign in with a Microsoft account and link it to the publisher.

Alternatively, login using:

```bash
vsce login <publisher-name>
```

### 3.2 Publish

To publish the extension:

```bash
vsce publish
```

To publish a specific version:

```bash
vsce publish <version>
```

To publish a pre-packaged `.vsix` manually:

```bash
vsce publish --packagePath layout-saver-1.0.0.vsix
```

---

## Updating Your Extension

1. Update the `version` field in `package.json`
2. Re-run:

```bash
vsce package
vsce publish
```

---

## Test Locally

Before publishing, test the `.vsix` file locally:

```bash
code --install-extension layout-saver-1.0.0.vsix
```

To uninstall:

```bash
code --uninstall-extension <publisher>.<extension-name>
```

---

## Resources

* [VS Code Extension Docs](https://code.visualstudio.com/api)
* [VSCE CLI GitHub](https://github.com/microsoft/vsce)
* [Marketplace Manage](https://marketplace.visualstudio.com/manage)