# tailwindcss-vscode-setup
# Tailwind CSS IntelliSense Setup for VS Code

This repository provides a step-by-step guide to configuring Tailwind CSS IntelliSense in Visual Studio Code. If you encounter issues with Tailwind CSS directives not being recognized or IntelliSense not working, follow these instructions to resolve them.

## Prerequisites

- **Node.js** installed on your machine.
- **VS Code** installed.
- A project set up with **Tailwind CSS** and **React** (using Vite as a bundler).

## Steps to Configure Tailwind CSS IntelliSense

### 1. Install Tailwind CSS and PostCSS

Ensure you have Tailwind CSS and PostCSS installed in your project. If not, run the following command:

2. Configure tailwind.config.js
Make sure your tailwind.config.js file is correctly set up:

/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}

3. Configure postcss.config.js
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}

4. Add Tailwind CSS Directives in index.css

@tailwind base;
@tailwind components;
@tailwind utilities;

5. Update VS Code Settings

{
  "css.validate": false,
  "less.validate": false,
  "scss.validate": false,
  "tailwindCSS.includeLanguages": {
    "plaintext": "html",
    "javascript": "javascript",
    "javascriptreact": "javascript",
    "typescript": "javascript",
    "typescriptreact": "javascript"
  },
  "editor.quickSuggestions": {
    "strings": true
  },
  "tailwindCSS.emmetCompletions": true
}

6. Install Tailwind CSS IntelliSense Extension
Install the Tailwind CSS IntelliSense extension from the VS Code marketplace.

7. Restart VS Code
Close and reopen Visual Studio Code to ensure all settings are applied.

8. Verify IntelliSense
Open a React component and start typing Tailwind CSS classes in the className attribute to verify that IntelliSense suggestions appear.

Example React Component
Here's an example of a React component using Tailwind CSS:
import React from 'react';
import './index.css';

function App() {
  return (
    <div className="flex items-center justify-center min-h-screen bg-gray-200">
      <h1 className="text-4xl font-bold text-blue-600">
        Welcome to Vite + React + Tailwind CSS!
      </h1>
    </div>
  );
}

export default App;

Running the Project
Ensure Vite is running to serve your React project:
npm run dev


