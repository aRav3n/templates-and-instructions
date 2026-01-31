# Set Up Node

## Initial Setup:

1.  Create your repo in GitHub
2.  In the parent directory
    1.  ```bash
        git clone [SSH from GitHub]
        ```
3.  cd to the newly created directory
4.  ```bash
     npm init -y
     
     npm install express express-validator
     npm install dotenv pg
     npm install bcryptjs
     npm install cors
     npm install jsonwebtoken
     npm install @prisma/client
     
     npm install jest --save-dev
     npm install supertest --save-dev
     npm install prisma --save-dev
     npm install typescript --save-dev
     npm install tsx --save-dev
     npm install @types/node --save-dev
     
     mkdir routes controllers db public src
     touch app.js routes/router.js controllers/controller.js src/queries.ts
     
     code package.json
    ```
5.  Verify that package.json looks correct
    1.  ```json
        "dependencies": {
            "@prisma/client": "^6.8.2",
            "bcryptjs": "^3.0.2",
            "cors": "^2.8.5",
            "dotenv": "^16.5.0",
            "express": "^5.1.0",
            "express-validator": "^7.2.1",
            "jsonwebtoken": "^9.0.2",
            "pg": "^8.16.0"
          },
          "devDependencies": {
            "@types/node": "^22.15.18",
            "jest": "^29.7.0",
            "prisma": "^6.8.2",
            "supertest": "^7.1.1",
            "tsx": "^4.19.4",
            "typescript": "^5.8.3"
          }
        ```
6.  Update "scripts" in package.json
    1.  ```json
         "scripts": {
             "dev": "npx tsc && NODE_ENV=development && node --watch app.js",
             "test": "npx tsc && NODE_ENV=test && jest"
           },
        ```
7.  ```bash
    touch .gitignore
    code .gitignore
    ```
    1.  Paste emmet template into the file
8.  ```bash
    code app.js routes/router.js controllers/controller.js 
    ```
    1.  Past in emmet templates
9.  ```bash
    git add .
    git commit
    ```
    1.  build: create initial app structure
10. ```bash
    git push origin main
    ```

### Set Up PostgreSQL database:

1.  ```bash
    psql
    ```
2.  ```bash
    CREATE DATABASE database_name;
    ```
3.  Verify that you created the database successfully
    1.  ```bash
        \c database_name
        ```
4.  ```bash
    \q
    ```
5.  If you're using Prisma this is as far as you need to go with the database, you may now continue to **Set Up Prisma**
6.  If not using Prisma, the rest of the instructions can be found [here](https://www.theodinproject.com/lessons/nodejs-using-postgresql)

### Set Up Prisma (Optional):

1.  ```bash
    npx tsc --init  
    npx prisma  
    npx prisma init  
    code .env
    ```
    1.  ```.env
        NODE_ENV=development
        TEST_DATABASE_URL="postgresql://andy:littleann@localhost:5432/DATABASE_NAME"
        DEV_DATABASE_URL="postgresql://andy:littleann@localhost:5432/DATABASE_NAME"
        DATABASE_URL="paste URL from cloud here (may have to temporarily set this to TEST and DEV addresses to set up the tables"
        SECRET_KEY="c4ts_R_cUt3"
        ```
2.  ```bash
     code prisma/schema.prisma
    ```
    1.  Create database schema by following the instructions [here](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases/using-prisma-migrate-typescript-prismaPostgres)
    2.  Add **binaryTargets**
        1.  ```prisma
            generator client {
              provider      = "prisma-client-js"
              binaryTargets = ["native", "debian-openssl-3.0.x"]
              output        = "../generated/prisma"
            }
            ``` 
3.  ```bash
    npx prisma migrate dev --name init
    npm install @prisma/client
    npm install @prisma/extension-accelerate
    ```
4.  ```bash
    npx prisma generate
    ```
5.  ```bash
    code tsconfig.json
    ```
    1.  Replace all the text with the **tsconfigprisma** emmet snippet

## During build:

- Test the software frequently
    - ```bash
      npm run test
      ```
- Run this to manually compile queries.ts
    - ```bash
      npx tsc
      ```
- Don't use **done** with **async** tests, instead:
    - ```js
      test("async test", async () => {
         const res = await request(app)
           .doStuff
      
         const token = res.body.token;
      
         // must AWAIT all requests inside an async test
         await request(app) 
           .doStuff
      });
      ```
- After making any updates to the Prisma schema be sure to push them to the actual database
    - ```bash
      npx prisma migrate dev --name <name>
      ```
## Deployment

1.  If this will be an API backend
    1.  In **app.js** update the CORS allowList to include the frontend URL
        1.  Make sure that there are no trailing slashes at the end of the URLs
    2.  In **.env**
        1.  Change the environment to **production**
2.  ```bash
    git add .
    git commit
    ```
3.  ```bash
    build: add cloud frontend to CORS allowList
    ```
4.  ```bash
    git push origin main
    ```
5.  Set up the cloud database:
6.  Go to the [Neon website](https://console.neon.tech/app/projects)
7.  Sign in
8.  Click the **New Project** button
9.  Fill in the name
10. Click **Create project**
11. Click the **Connect** button
12. Copy the database address
13. Go to the IDE
    1.  Open your **.env** file and add a line that says **DATABASE_URL=**
    2.  Paste the database address into your **.env** file for the \*\*DATABASE_URL \*\*variable
14. *==For a raw SQL database==*
    1.  In pool.js under module.exports comment out all the lines inside **new Pool({})**
    2.  Enter as the only uncommented line inside Pool
    3.  ```js
        connectionString: process.env.DATABASE_URL, 
        ```
    4.  Add to the top of pool.js
        1.  ```js
            require("dotenv").config();
            ```
    5.  In your IDE run the file you use to create and populate your tables
15. *==For a Prisma database==*
    1.  Enter the following into the terminal
        - ```bash
          npx prisma migrate dev --name add_database_to_neon
           ```
    2.  If you get a popup from Little Snitch hit **Allow**
    3.  ```bash
        npx prisma generate
        ```
    4.  ```bash
        git add .
        git commit
        ```

        ```git
        build: set up Prisma for the cloud
        ```

    5.  ```bash
        git push origin main
        ```
    6.  Verify that everything works
16. Set up the project in the cloud
    1.  Go to the [Render dashboard](https://dashboard.render.com/)
    2.  Click **\+ Add New** then **Web Service**
    3.  Click **Credentials** then the **Github menu** then **Configure in GitHub**
    4.  After signing in go to the repositories section and click the dropdown for **Selected Repositories** and pick the repo that you want to deploy from
    5.  In Render you can now pick the repo you want to deploy
    6.  Click **Connect**
    7.  Type in a name
    8.  Change build command to **npm install**
    9.  Change start command to **node app.js**
    10. Select the free tier
    11. Add your .env variables
    12. Click **Deploy Web Service**
    13. Wait a bit and verify that it works
    14. If this is an API, add the address to your frontend
