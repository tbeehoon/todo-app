# NVM, React and Vite

Compiled  by Tan Bee Hoon (contact: tbeehoon@gmail)

This guide shows how to set up a Node.js environment managed by **NVM** so you can build React apps with **Vite**.

## 1. Install NVM (Node Version Manager)

Download the latest `nvm-setup.exe` from the releases page: https://github.com/coreybutler/nvm-windows/releases

Run the installer, then open a new PowerShell/Command Prompt.

Verify:

```
nvm -version
```

> [!TIP]
>
> Avoid installing the “global” Node.js from nodejs.org if using NVM. 



## 2. Install Node.js via NVM and set a default

Install the version required (LTS recommended), then make it the default so new terminals pick it automatically.

```
# Install latest LTS
nvm install --lts

# OR install a specific version
nvm install 20

# Use it now
nvm use 20

# Make it the default for all new shells
nvm alias default 20
```

In bash, do verification. 

```
# Verify
node -v
npm -v
```



## 3. Create a new React app with Vite

From any workspace folder in your terminal:

```
npm create vite@latest my-app -- --template react
# For TypeScript:
# npm create vite@latest my-app -- --template react-ts
```

Then install dependencies and run the dev server:

```
cd my-app
npm install
npm run dev
# Vite typically starts at http://localhost:5173
```

> [!TIP]
>
> Ctl-C to stop



## 4. Add Bootstrap to the React project

Install Bootstrap and its dependencies:

```
npm install bootstrap react-bootstrap
```

Import Bootstrap styles in src/main.jsx` (or `src/main.tsx` for TypeScript):

```
import 'bootstrap/dist/css/bootstrap.min.css'
```

Ready to use Bootstrap classes and React-Bootstrap components in app.

Example in `App.jsx`:

```
import Button from 'react-bootstrap/Button'

function App() {
return (
<div className="p-4">
    <h1>Hello, Bootstrap + React + Vite!</h1>
    <Button variant="primary">Click Me</Button>
</div>
)
}

export default App
```



## 5. Initialize Git

Version control the project using Git.

```
# Initialize a git repository
git init

# Add all project files
git add .

# Commit the files
git commit -m "Initial commit: setup React + Vite project"
```

To add to Github.

```
# Add remote 
git remote add origin https://github.com/username/my-app.git

# Push changes
git branch -M main
git push -u origin main
```

In case identity need to be authenticated:

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```



## 6. Setup .gitignore

Add a `.gitignore` file in the root of the project to exclude files and folders not required in version control:

```
# dependencies
/node_modules

# production build
/dist

# logs
npm-debug.log*
*.log

# environment variables
.env
.env.local
.env.*.local

# IDE/editor folders
.vscode/
.DS_Store

# Vite cache
.vite/
```

@Q.E.D.