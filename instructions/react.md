# React Setup

## Table of Contents

- [Initial Setup](#initial-setup)
- [Troubleshooting](#troubleshooting)
- [Publishing](#publishing)
  - [Adding a Custom Domain](#adding-a-custom-domain)

## Initial Setup:

1.  `cd` into your preferred parent directory
2.  In parent directory run these commands

    ```
    npm create vite@latest APP_NAME -- --template react
    ```
    - Or for a project built with TypeScript:
        ```
        npm create vite@latest APP_NAME -- --template react-ts
        ```


    ```
    cd APP_NAME
    ```

    ```
    npm install
    code .gitignore
    ```

3.  Select all and paste the gitignore emmet snippet
4.  In GitHub
    1.  Create a new **empty** repo in GitHub
    2.  Paste the code from **…or create a new repository on the command line** into your IDE terminal and run it
5.  Install the [eslint-prettier](https://github.com/prettier/eslint-config-prettier?tab=readme-ov-file#installation) config

    ```
    npm i -D eslint-config-prettier
    code eslint.config.js
    ```

6.  ```
    export default [
      { extends: ["prettier"] },
      ....
      eslintConfigPrettier,
    ]);
    ```
7.  ```
     git add .
     git commit
    ```

    ```
    build: initialize React project

    - Install React + Vite
    - Install NPM packages
    - Set up ESLint-Prettier config
    ```

8.  ```
    git push origin main
    ```
9.  In the GitHub repo
    1.  Click **Add File** > **Create new file**
    2.  In the file name field, type **LICENSE** (all uppercase).
    3.  Under the file name, click **Choose a license template**
    4.  Select MIT License
    5.  Submit with this commit message:

        ```
        chore: add license file
        ```

10. ```
    git pull origin main
    ```

## Troubleshooting

- If input element deselects after typing
  - It's likely that a nested React element is re-rendered due to a state change. Move the function outside of its parent.
    - ```
      i.e. change Payment(){ CashPayment(){} } to CashPayment(){} Payment(){}
      ```

## Publishing:

1.  git push origin main
2.  Log in to [cloudflare](https://dash.cloudflare.com/login)
3.  At the top click **\+ Add**
4.  Click **Pages**
5.  Click **Import an existing Git repository**
6.  Select the correct repo
7.  Click **Begin setup**
8.  **Build command**
    1.  npm run build
9.  **Build output directory**
    1.  dist
10. **Environment variables (advanced)**
    1.  \+ Add variable
        1.  **Variable name**
            1.  NODE_VERSION
        2.  **Value**
            1.  run **node -v** in your terminal, this number (i.e. v22.13.1) is the value
11. Click **Save and deploy**
12. If your project is connecting to an API you build make sure to update the backend's CORS settings

## Adding a Custom Domain

1.  Once published go to your **Account Home** on Cloudflare
2.  Change from the **Domains** tab to the **Developer Platform** tab
3.  Open the project that you want to add a custom domain for
4.  Go to the **Custom domains** tab
5.  Click **Set up a custom domain** and follow the instructions
