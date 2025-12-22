# React Native Setup

## Initial Setup

1.  Install [Expo Go](https://expo.dev/go) on your device if you don't already have it
2.  In parent directory
    - ```bash
      npx create-expo-app@latest PROJECT_NAME
      ```
3.  ```bash
    cd PROJECT_NAME
    ```
4.  [Create a new **empty** repo in GitHub](https://github.com/new) and follow the instructions to link the new app folder
5.  Follow the **…or push an existing repository from the command line** instructions
6.  ```bash
    git push origin main
    ```
7.  In the GitHub repo click **Add File** > **Create New File**
8.  In the file name field, type `LICENSE` (all uppercase).
9.  Under the file name, click **Choose a license template**
10. Select the desired license
11. Submit with this commit message:
    - ```bash
      chore: add license
      ```
12. ```bash
    git pull origin main
    ```
13. ```bash
    npx expo start --tunnel
    ```
14. Update the README using the [template](https://github.com/aRav3n/readme_template)
    1.  ```bash
        code README.md
        ```
    2.  Copy [my README Template](https://github.com/aRav3n/doc_templates/blob/main/README.md?plain=1)
    3.  Paste it into README.md
    4.  ```bash
        git add .
        git commit
        ```

        ```git
        docs: update README using my template
        ```

        ```bash
        git push origin main
        ```
15. Start building the project  
    1\. [Setup instructions](https://docs.expo.dev/tutorial/create-your-first-app/)

## Prisma Setup

1.  Install dependencies
    - ```bash
      npx expo install @prisma/client
      npx expo install @prisma/react-native
      npx expo install react-native-quick-base64
      npm install @prisma/config
      ```
1.  Update app.json
    - ```bash
      {
        "expo": {
          // ... The rest of your expo config
          "plugins": ["@prisma/react-native"]
        }
      }
      ```
1.  To activate the Prisma plugin run:
    - ```bash
      npx expo prebuild --clean
      ```
1.  ```bash
    code schema.prisma
    ```
    - ```prisma
      generator client {
        provider = "prisma-client-js"
        previewFeatures = ["reactNative"]
      }

      datasource db {
        provider = "sqlite"
      }

      // Your data model

      model User {
        id           Int     @id @default(autoincrement())
        name         String
      }
      ```
1.  ```bash
    code prisma.config.ts
    ```
    - ```ts
      import { defineConfig } from "@prisma/config";

      export default defineConfig({
        schema: "schema.prisma",
        datasource: {
          url: "file:./app.db",
        },
      });
      ```
1.  Generate the Prisma databases:
    - ```bash
      npx prisma@latest migrate dev
      npx prisma@latest generate
      ```
1.  Create your queries.ts file
    - ```ts
      import { PrismaClient } from "@prisma/client";
      import { reactiveHooksExtension } from "@prisma/react-native";
      import "@prisma/react-native";

      const baseClient = new PrismaClient();

      export const extendedClient = baseClient.$extends(
        reactiveHooksExtension()
      );
      ```

# Publishing

## Github

- Set up the **apk** build profile in eas.json
  - ```json
    ...
    "build": {
      "apk": {
        "android": {
        "buildType": "apk"
        }
      },
      ...
    },
    ...
    ```
- ```bash
  eas build -p android --profile apk
  ```
- Download the built app
- In the repo click **Releases** on the right hand side
- Click **Draft a new release**
- Fill everything out and add the apk

## Obtanium

- In the **Obtanium** app click **Add app**
- Paste your repo's url
- Install the app
- Long press on the app in the Obtanium **Apps list**
- Hit the **...** button
- **Share app configuration as HTML link**
- Copy it and paste into a note app to transfer it to your computer
- Update the Obtanium link in your Readme with the new **HTML link** (the link should currently be commented out if you used the template)

## Web Deployment

Follow the instructions [here](https://docs.expo.dev/deploy/web/)
