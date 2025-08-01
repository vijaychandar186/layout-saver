npm install -g @vscode/vsce

@vijaychandar186 ➜ /workspaces/layout-saver (main) $ vsce package
Executing prepublish script 'npm run vscode:prepublish'...

> layout-saver@1.0.0 vscode:prepublish
> pnpm run esbuild-base --pure:console.log --minify


> layout-saver@1.0.0 esbuild-base /workspaces/layout-saver
> esbuild ./src/extension.ts --bundle --outfile=out/main.js --external:vscode --format=cjs --platform=node --pure:console.log --minify


  out/main.js  2.5kb

⚡ Done in 6ms
 WARNING  Neither a .vscodeignore file nor a "files" property in package.json was found. To ensure only necessary files are included in your extension, add a .vscodeignore file or specify the "files" property in package.json. More info: https://aka.ms/vscode-vscodeignore

 INFO  Files included in the VSIX:
layout-saver-1.0.0.vsix
├─ [Content_Types].xml 
├─ extension.vsixmanifest 
└─ extension/
   ├─ .gitignore [2.1 KB]
   ├─ LICENSE.txt [34.32 KB]
   ├─ package.json [1.81 KB]
   ├─ pnpm-lock.yaml [8.7 KB]
   ├─ readme.md 
   ├─ .vscode/
   │  ├─ launch.json [0.41 KB]
   │  └─ tasks.json [0.58 KB]
   ├─ out/
   │  └─ main.js [2.48 KB]
   └─ src/
      └─ extension.ts [3.29 KB]

 DONE  Packaged: /workspaces/layout-saver/layout-saver-1.0.0.vsix (11 files, 22.16 KB)