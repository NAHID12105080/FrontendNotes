# Initializing a TypeScript Project
### **Using a Bundler:(vite)**

### First create a new vite project:
```sh
npm create vite@latest .
```
 select &darr;  vanila-> typescript
                 

```sh
npm i 
npm run dev
npm run build
```
### to see a production build
```sh
npm run preview 
```

## Follow these steps to initialize a TypeScript project manually using the CLI:
1. **Initialize a new Node.js project:**
   ```sh
   npm init -y
   ```
2. Install TypeScript as a development dependency:

```sh
npm install --save-dev typescript
```

3. Create a TypeScript configuration file:
```sh
npx tsc --init
```
4. Compile the TypeScript file:
```sh
npx tsc index.ts(name of the file u want to compile)
```

