## Requirements
```
wsl -l -v
  NAME              STATE           VERSION
  Ubuntu            Running         2

lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.3 LTS
Release:        24.04
Codename:       noble

node --version
v18.19.1

```

## Installation based on Co-pilot
**Prompt:** *install node with express and typescript*

```
mkdir express-ts && cd express-ts
npm init -y
npm install express typescript @types/express @types/node
npx tsc --init
mkdir src
```

changed to tsconfig.json
```
    "rootDir": "./src",
    "outDir": "./dist",

    "module": "commonjs",
    "target": "es2017",
    "types": ["node"],

    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    // "verbatimModuleSyntax": true,    
```

Compile typescript
```
npx tsc
```

Update packages.json
```
  "main": "dist/app.js",
   "scripts": {
    "build": "tsc",
    "start": "node dist/app.js",
    "dev": "tsc && node dist/app.js"
   },
```

Running
```
# build
npm run build

# start server
npm start

# build and start
npm run dev

```

## Copilot Instructions

The Node.js project with Express and TypeScript has been successfully set up in the express-ts workspace. Here's what was installed and configured:

**Dependencies:** Express, TypeScript, and type definitions for Express and Node.js.
**Project Structure:**
- `package.json`: Configured with build, start, and dev scripts.
- `tsconfig.json`: TypeScript config with esModuleInterop enabled for Express compatibility.
- `app.ts`: A basic Express server that responds with "Hello World with TypeScript and Express!" on port 3000.
- `dist`: Compiled JavaScript output.

To run the project:
1. Build: npm run build (compiles TypeScript).
2. Start: npm start (runs the server).
3. Or use npm run dev for a combined build and run.

The server will be accessible at http://localhost:3000. The README.md has been updated with usage instructions.


## Adding Static Server

**Prompt:** *create a folder called static to so static files can be served*

The static folder has been created in the project root. The Express app has been updated to serve static files from this folder using `app.use(express.static('static'));`.

A sample index.html file has been added to the static folder as an example. After rebuilding with npm run build, you can place any static files (HTML, CSS, JS, images, etc.) in the static folder, and they will be accessible via http://localhost:3000/filename when the server is running.

For example, the sample index.html can be viewed at http://localhost:3000/index.html.