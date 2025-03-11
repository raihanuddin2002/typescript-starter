npm init -y
npm i --save-dev typescript ts-node ts-node-dev tsc-alias tsconfig-paths @types/node 

or

pnpm i -D typescript ts-node ts-node-dev tsc-alias tsconfig-paths @types/node 

### **Setup The Development Environment**

---

**Step 1:** Create a npm project

**Step 2:** Install the following dependencies -

- `typescript`: TypeScript compiler and essential tooling.
- `ts-node`: A TypeScript execution engine for Node.js, useful for running TypeScript directly.
- `ts-node-dev`: A faster version of `ts-node`, useful for development as it supports hot-reloading.
- `tsc-alias`: A package to handle custom path aliases.
- `tsconfig-paths`: A helper for resolving custom TypeScript path aliases.

**Step 3:** Install `@types/node` for built in node modules types

**Step 4:** Create a **tsconfig.json** file

```jsx
{
  "compilerOptions": {
    "target": "ES2020",                 // Target modern JavaScript
    "module": "commonjs",               // Use commonjs module system
    "strict": true,                     // Enable strict type checking
    "esModuleInterop": true,            // Ensure compatibility with CommonJS and ES modules
    "skipLibCheck": true,               // Skip library checks for faster build times
    "forceConsistentCasingInFileNames": true, // Ensure consistent casing in imports
    "outDir": "./dist",                 // Output directory for compiled JavaScript
    "rootDir": "./src",                 // Root directory for your TypeScript source files
    "baseUrl": ".",                     // Set the base URL for module resolution
    "paths": {
      "@src/*": ["src/*"]               // Configure path aliases
    }
  },
  "include": ["src/**/*.ts"],            // Include all .ts files in the src folder
  "exclude": ["node_modules"]            // Exclude node_modules from compilation
}

```

**Step 5:** Create the `src/index.ts` file

**Step 6:** Update the npm scripts

```jsx
"scripts": {
  "start": "ts-node -r tsconfig-paths/register src/index.ts",
  "dev": "ts-node-dev -r tsconfig-paths/register src/index.ts",
  "build": "tsc && tsc-alias"
}

```

**Step 7:** Run and test

**Step 8:** Add a debug launch script `.vscode/launch.json`