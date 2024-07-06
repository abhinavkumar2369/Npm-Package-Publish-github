## Overview 🚀

- To create and publish a package to GitHub Packages using a JavaScript (or TypeScript) library as an example, follow these steps.
- This guide assumes you already have a GitHub account and have Git installed on your machine.


## 1: Prepare Your Project 📝

1. **`Initialize your project`** (if you haven't already) by running npm init in your project directory.
2. **`Create your library`**: Implement the functionality you wish to provide. For example, a simple function in index.js.



## 2: Configure Your Package for GitHub Packages ⚒️

1. **`Login to GitHub`** and create a new repository for your package.
2. **`Configure package.json:`**
- **`name:`** Must match the format `@your-github-username/your-package-name`. GitHub Packages requires scoped package names.
- **`repository:`** Specify the URL of your GitHub repository.
- **`publishConfig:`** Add a section for GitHub Packages URL.
  Example package.json adjustments:
  ```js
  {
  "name": "@your-github-username/your-package-name",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/your-github-username/your-package-name.git"
  },
  "publishConfig": {
    "registry": "https://npm.pkg.github.com/"
  },
  "author": "",
  "license": "ISC"
  }
  ```




## 3: Authenticate with GitHub Packages

1. - Generate a personal access token (PAT) on GitHub with `write:packages`, `read:packages`, and `delete:packages` (if necessary) scopes.
   - Include `repo` scope if your repository is private.
2. Login to npm using your GitHub PAT:
   ```bash
   npm login --registry=https://npm.pkg.github.com --scope=@your-github-username
   ```
  - Username: your GitHub username
  - Password: your GitHub PAT
  - Email: your GitHub email





## 4: Publish Your Package
  - Run the following command in your project directory:
    ```bash
    npm publish
    ```




## 5: Using Your GitHub Package
  - To use your package in a project, you need to configure the project to use GitHub Packages.

  1. Create or edit an `.npmrc` file in your project root (or your home directory for global configuration) to include:
    ```
    @your-github-username:registry=https://npm.pkg.github.com
    ```

  3. Install your package in your project:
    ```
    npm install @your-github-username/your-package-name
    ```

- Remember to replace `your-github-username` and `your-package-name` with your actual GitHub username and your package's name.
