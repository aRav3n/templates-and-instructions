# App Name

## Table of Contents

- [Description](#description)
- **For End Users**
  - [Where to View on the Web](#where-to-view-on-the-web)
  - [Usage and Screenshots](#usage-and-screenshots)
- **For Developers**
  - [Future Improvements](#future-improvements)
  - [Installation Instructions](#installation-instructions)
  - [Technologies Used](#technologies-used)
  - [Dependencies and Credits](#dependencies-and-credits)
  - [Project Structure](#project-structure)

## Description

Write a paragraph or two describing the project here.

### Features

- Feature one
- Feature two

## Where to View on The Web

<!-- ******** Add link ************
[Try it out online](LINK_TO_WEB_DEPLOYMENT)
-->

## Usage and Screenshots

<img src="./public/screenshot.png" alt="screenshot" style="height: 50vh; width: auto;">

Here's a brief description of how to use the app.

- [Link to live preview](https://groundedwanderer.dev/)
- [Link to backend repo](https://github.com/aRav3n/odin-book-backend)

## Future Improvements

- Improvement idea

## Installation Instructions

1. If you haven't already, [install Node.js and npm](https://www.theodinproject.com/lessons/foundations-installing-node-js)
   - Note that installing Node.js [also installs npm](https://www.theodinproject.com/lessons/foundations-installing-node-js#step-2-setting-the-node-version)
1. Fork this repo
1. In your copy of the repo click the green **Code** button and copy the URL
1. Open your IDE
1. `cd PARENT_DIRECTORY_FOR_THIS_PROJECT`
1. `git clone COPIED_URL`
1. `cd PROJECT_FOLDER`
1. Run the following in your terminal
   - ```bash
     npm init -y
     npm install
     ```
1. If running the API locally
   1. Find the URL
      - For a Node.js / Express app this would be in: _backend_folder/app.js_ at the bottom
   2. Update the API URL
      - ```bash
        code src/functions/apiCommunication.js
        ```
      - Update `const apiUrl` with the new URL. (It is likely http://localhost:3000)
        - Be sure to remove the trailing "/" if there is one
1. ```bash
   npm run dev
   ```

   - `^` + `c` will end the process

1. Navigate to the url displayed in the terminal: `➜  Local:   http://localhost:5173/`

## Technologies Used

- <a href="https://developer.mozilla.org/en-US/docs/Web/CSS"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" style="height: 2rem; width: auto;"> CSS</a>
- <a href="https://eslint.org/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/eslint/eslint-original.svg" style="height: 2rem; width: auto;"> ESLint</a>
- <a href="https://developer.mozilla.org/en-US/docs/Web/HTML"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" style="height: 2rem; width: auto;"> HTML</a>
- <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" style="height: 2rem; width: auto;"> JavaScript</a>
- <a href="https://www.prisma.io/"><img src="https://skillicons.dev/icons?i=prisma" style="height: 2rem; width: auto;"/> Prisma ORM</a>
- <a href="https://react.dev/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" style="height: 2rem; width: auto;"> React</a>
- <a href="https://www.typescriptlang.org/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" style="height: 2rem; width: auto;"/> TypeScript</a>
- <a href="https://vite.dev/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vitejs/vitejs-original.svg" style="height: 2rem; width: auto; vertical-align: middle;"> Vite </a>

### Development Tools

- <a href="https://code.visualstudio.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vscode/vscode-original.svg" style="height: 24px; width: auto;"/> VS Code</a>
- <a href="https://www.npmjs.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/npm/npm-original.svg" style="height: 24px; width: auto;"/> npm</a>
- <a href="https://git-scm.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" style="height: 24px; width: auto;"/> Git</a>

### Hosting

- <a href="https://www.cloudflare.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/cloudflare/cloudflare-original.svg" style="height: 24px; width: auto;"/> Cloudflare</a>
- <a href="https://github.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg" style="height: 24px; width: auto;"/> Github</a>

## Dependencies and Credits

### Package Dependencies

- [packageName](https://www.npmjs.com/package/packageName)

### Other Credits

- [Devicion](https://devicon.dev/)
- [Skillicons](https://skillicons.dev/)

## Project Structure

```bash
├──controllers/            # Controller files
├──db/                     # Compiled queries.js
├──generated/              # Generated Prisma files
├──prisma/                 # Prisma models and migrations
├──public/                 # Locally hosted images and icons
├──routes/                 # Router files
├──src/                    # Source files
    ├── controllers/       # Request handlers
    └── server.ts
└──test/                   # Test files
```
