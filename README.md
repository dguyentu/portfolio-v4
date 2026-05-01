<div align="center">
  <img alt="Logo" src="src/images/logo.svg" width="100" />
</div>
<h1 align="center">
  Daniel Tu - Portfolio
</h1>
<p align="center">
  The fourth iteration of my portfolio, built with <a href="https://www.gatsbyjs.org/" target="_blank">Gatsby</a> and hosted with <a href="https://pages.github.com/" target="_blank">GitHub Pages</a>.
</p>
<p align="center">
  Previous iterations:
  <a href="https://github.com/bchiang7/v1" target="_blank">v1</a>,
  <a href="https://github.com/bchiang7/v2" target="_blank">v2</a>,
  <a href="https://github.com/bchiang7/bchiang7.github.io" target="_blank">v3</a>
</p>

![demo](src/images/demo.png)

## 🚨 Forking this repo (please read!)

Many people have contacted me asking me if they can use this code for their own website, and the answer to that question is usually **yes, with attribution**.

I value keeping my site open source, but as you all know, _**plagiarism is bad**_. It's always disheartening whenever I find that someone has copied my site without giving me credit. I spent a non-trivial amount of effort building and designing this iteration of my website, and I am proud of it! All I ask of you all is to not claim this effort as your own.

Please also note that I did not build this site with the intention of it being a starter theme, so if you have questions about implementation, please refer to the [Gatsby docs](https://www.gatsbyjs.org/docs/).

### TL;DR

Yes, you can fork this repo. Please give me proper credit by linking back to [brittanychiang.com](https://brittanychiang.com). Thanks!

## 🛠 Installation & Set Up

1. Install the Gatsby CLI

   ```sh
   npm install -g gatsby-cli
   ```

2. Install and use the correct version of Node using [NVM](https://github.com/nvm-sh/nvm)

   ```sh
   nvm install
   ```

3. Install dependencies

   ```sh
   npm install
   ```

4. Start the development server

   ```sh
   npm start
   ```

## 🚀 Building and Running for Production

1. Generate a full static production build

   ```sh
   npm run build
   ```

1. Preview the site as it will appear once deployed

   ```sh
   npm run serve
   ```

## 🐛 Troubleshooting

If you encounter issues while setting up or running the project, here are some common problems and their solutions:

### 1. `ENOENT: no such file or directory, lstat '/Users/dantu/git/profile-v4/.cache'`

This error typically indicates a corrupted Gatsby cache or a conflict with filesystem operations.

**Solution:**

1.  **Ensure Correct Node.js Version:**
    This project requires Node.js `16.20.2`. Verify that you are using this version.

    ```sh
    nvm use
    node -v # Should output v16.20.2
    ```

    (If you don't have it, run `nvm install 16.20.2` first.)

2.  **Aggressive Cleanup:**
    Stop any lingering Node processes and manually remove the cache, public, and dependency folders.

    ```sh
    killall node # This might show "No matching processes..." which is fine.
    rm -rf .cache public node_modules package-lock.json
    ```

3.  **Reinstall Dependencies:**

    ```sh
    npm install
    ```

4.  **Manually Recreate Cache Folder:**
    The `tmp` library used by Gatsby often crashes if it attempts to resolve the real path of a directory that hasn't been initialized yet.

    ```sh
    mkdir .cache
    ```

5.  **Start Development Server via npx:**
    Using `npx` ensures you are using the project's local Gatsby version, bypassing potential conflicts with global `gatsby-cli` installations.
    ```sh
    npx gatsby develop
    ```

### 3. `Error in function useStaticQuery: The result of this StaticQuery could not be fetched.`

This error occurs when Gatsby's data layer is out of sync with the frontend. It is common after modifying markdown files or `gatsby-config.js`, especially if a previous process (a "zombie" process) didn't close properly and is still holding onto port 8000.

**Solution:**

1.  **Kill Zombie Processes:** Ensure no hidden node processes are running.

    ```sh
    killall node
    ```

2.  **Run Nuclear Reset:**

    ```sh
    npm run reinstall
    ```

3.  **Start Server:**
    ```sh
    npx gatsby develop
    ```

### 2. `Error: Cannot find module 'node:stream'`

This error occurs when a dependency tries to use the `node:` prefix for built-in modules, which is not supported in older Node.js versions (like v14).

**Solution:**

1.  **Update Node.js Version:** Ensure your `.nvmrc` is set to `16.20.2` and you are actively using it (`nvm use`).
2.  **Dependency Overrides:** The `package.json` has been updated with `overrides` for `cheerio` and `parse5-parser-stream` to pin them to compatible versions.
3.  **Clean and Reinstall:**
    ```sh
    rm -rf node_modules package-lock.json
    npm install
    ```
4.  **Start Development Server:**
    ```sh
    npm start
    ```

## 🎨 Color Reference

## 🎨 Color Reference

| Color          | Hex                                                                |
| -------------- | ------------------------------------------------------------------ |
| Navy           | ![#0a192f](https://via.placeholder.com/10/0a192f?text=+) `#0a192f` |
| Light Navy     | ![#112240](https://via.placeholder.com/10/0a192f?text=+) `#112240` |
| Lightest Navy  | ![#233554](https://via.placeholder.com/10/303C55?text=+) `#233554` |
| Slate          | ![#8892b0](https://via.placeholder.com/10/8892b0?text=+) `#8892b0` |
| Light Slate    | ![#a8b2d1](https://via.placeholder.com/10/a8b2d1?text=+) `#a8b2d1` |
| Lightest Slate | ![#ccd6f6](https://via.placeholder.com/10/ccd6f6?text=+) `#ccd6f6` |
| White          | ![#e6f1ff](https://via.placeholder.com/10/e6f1ff?text=+) `#e6f1ff` |
| Green          | ![#64ffda](https://via.placeholder.com/10/64ffda?text=+) `#64ffda` |
