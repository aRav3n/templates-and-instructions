# App Name

## Table of Contents

- [Description](#description)
- **For End Users**
  - [Where to Download](#where-to-download-the-app)
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

## Where to Download the App

<!-- ******** Add link ************
<a href="APP_DEPLOYMENT_URL"><img src="https://img.shields.io/badge/Try%20it%20Online-000000?style=for-the-badge&logo=globe&logoColor=white" style="height: 48px; width: auto;"/></a>
-->

<!-- ******** Add link ************
<a href="https://play.google.com/store/games"><img src="https://upload.wikimedia.org/wikipedia/commons/7/78/Google_Play_Store_badge_EN.svg" style="height: 48px; width: auto;"/></a>
-->

<!-- ******* Need to get link to badge per: https://f-droid.org/docs/Badges/ ******
<a href="https://f-droid.org/packages/"><img src="" style="height: 48px; width: auto;"/></a>
-->

## Usage and Screenshots

### Screenshots of the Web App

<div>
<img src="./assets/images/screenshot.jpg" alt="screenshot" style="max-height: 50vh; max-width: 50vw;">
<img src="./assets/images/screenshot.jpg" alt="screenshot" style="max-height: 50vh; max-width: 50vw;">
</div>

### Screenshots of the Android App

<div>
<img src="./assets/images/screenshot.jpg" alt="screenshot" style="max-height: 50vh; max-width: 50vw;">
<img src="./assets/images/screenshot.jpg" alt="screenshot" style="max-height: 50vh; max-width: 50vw;">
</div>

Here's a brief description of how to use the app.

## Future Improvements

- Improvement idea

## Installation Instructions

1. If you haven't already, [install Node.js and npm](https://www.theodinproject.com/lessons/foundations-installing-node-js)
   - Note that installing Node.js [also installs npm](https://www.theodinproject.com/lessons/foundations-installing-node-js#step-2-setting-the-node-version)
1. Fork this repo
1. In your copy of the repo click the green **Code** button and copy the URL
1. If you don't have an Expo account [sign up](https://expo.dev/signup) for one
1. Open your IDE
1. `cd PARENT_DIRECTORY_FOR_THIS_PROJECT`
1. `git clone COPIED_URL`
1. `cd PROJECT_FOLDER`
1. Run the following in your terminal
   ```bash
   npm init -y
   npm install
   ```
   ```bash
   eas login
   ```
1. ```bash react native
   npx expo start
   ```

   - If there are [issues](https://docs.expo.dev/get-started/start-developing/#having-problems) run this instead
     ```bash
     npx expo start --tunnel
     ```
   - `^` + `c` will end the process

**Note: to build a production apk:**

1. ```bash
   code eas.json
   ```
1. ```bash
   {
    ...
    "build": {
      "apk": {
        "android": {
          "buildType": "apk"
        }
      },
   ...
   }
   ```
1. Then you can run the apk build profile
   ```
   eas build --platform android --profile apk
   ```

## Technologies Used

- <a href="https://developer.mozilla.org/en-US/docs/Web/CSS"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" style="height: 2rem; width: auto;"> CSS</a>
- <a href="https://eslint.org/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/eslint/eslint-original.svg" style="height: 2rem; width: auto;"> ESLint</a>
- <a href="https://expo.dev"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/expo/expo-original.svg" style="height: 2rem; width: auto; vertical-align: middle;"> Expo </a>
- <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" style="height: 2rem; width: auto;"> JavaScript</a>
- <a href="https://www.postgresql.org/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original.svg" style="height: 2rem; width: auto;"/> PostgreSQL</a>
- <a href="https://www.prisma.io/"><img src="https://skillicons.dev/icons?i=prisma" style="height: 2rem; width: auto;"/> Prisma ORM</a>
- <a href="https://reactnative.dev/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg" style="height: 2rem; width: auto;"> React Native</a>
- <a href="https://sqlite.org//"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sqlite/sqlite-original.svg" style="height: 2rem; width: auto;"/>SQLite</a>
- <a href="https://www.typescriptlang.org/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/typescript/typescript-original.svg" style="height: 2rem; width: auto;"/> TypeScript</a>

### Development Tools

- <a href="https://code.visualstudio.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vscode/vscode-original.svg" style="height: 24px; width: auto;"/> VS Code</a>
- <a href="https://www.npmjs.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/npm/npm-original.svg" style="height: 24px; width: auto;"/> npm</a>
- <a href="https://git-scm.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/git/git-original.svg" style="height: 24px; width: auto;"/> Git</a>

### Hosting

- <a href="https://expo.dev/services/hosting"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/expo/expo-original.svg" style="height: 24px; width: auto;"/> EAS</a>
- <a href="https://github.com/"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original.svg" style="height: 24px; width: auto;"/> Github</a>
- <a href="https://neon.com/"><img src="https://neon.com/brand/neon-logomark-light-color.svg" style="height: 24px; width: auto;"/> Neon</a>

## Dependencies and Credits

### Package Dependencies

- [packageName](https://www.npmjs.com/package/packageName)

### Other Credits

- [Devicion](https://devicon.dev/)
- [Skillicons](https://skillicons.dev/)

## Project Structure

<!-- make sure to add spaces in front of file names -->

```bash
├── assets/
   └── images/                      # Image files
        ├──
        └──
├── scripts/
├── src/
    ├── app/
        ├──(tabs)
            ├──
            ├──
            └──
        ├── api/                    # API routes in a separate folder
            ├──
            └──
        ├──
        └──
    ├── components/
        ├── styleThemes.ts          # general style themes like spacings, fonts, color palette, etc.
        ├──
        └──
    ├── screens/
        ├── home/
            ├──
            └──
        ├──
        └──
    ├── server/                     # code used in /api
        ├── auth.ts
        └── db.ts
    ├── utils/                      # reusable utilities
        ├──
        └──
    ├── hooks/
        ├──
        └──
├── LICENSE
├── app.json
├── eslint.config.js
├── package-lock.json
├── package.json
├── README.md
└── tsconfig.js
```
