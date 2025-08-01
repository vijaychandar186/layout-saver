# Publishing Your VS Code Extension

This guide walks you through packaging and publishing your VS Code extension using `@vscode/vsce`.

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

Make sure your extension has the following:

* `package.json` with `name`, `displayName`, `description`, `version`, `publisher`, `engines.vscode`, and `categories`
* `out/main.js` or compiled source

Then package the extension:

```bash
vsce package
```

This will create a `.vsix` file:

```
layout-saver-1.0.0.vsix
```

Example Output:

```
Files included in the VSIX:
layout-saver-1.0.0.vsix
├─ [Content_Types].xml
├─ extension.vsixmanifest
└─ extension/
   ├─ LICENSE.txt
   ├─ package.json
   ├─ readme.md
   └─ out/
      └─ main.js
```

---

## Step 3: Publish the Extension

### 3.1 Create a Publisher (first time only)

```bash
vsce create-publisher <publisher-name>
```

You'll be prompted to sign in with a Microsoft account.

### 3.2 Publish

```bash
vsce publish
```

To publish a specific version:

```bash
vsce publish <version>
```

To publish a `.vsix` manually:

```bash
vsce publish --packagePath layout-saver-1.0.0.vsix
```

---

## Updating Your Extension

1. Bump version in `package.json`
2. Re-run:

   ```bash
   vsce package
   vsce publish
   ```

---

## Test Locally

Before publishing, test your `.vsix`:

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