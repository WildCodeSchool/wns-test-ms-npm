# Publish a npm package

## Steps

### Initialize and publish

- initialize a new npm project
```shell
npm init -y
```

- change the name in package.json to `@organization/project`
- initialize git repository and commit
- publish your package

```shell
npm login
npm publish --access public
```

- check your profile on https://www.npmjs.com/

### Write a typecript package

- create `tsconfig.json`

```shell
tsc --init
```

- install dependencies
```shell
npm install typescript del-cli --save-dev
```

- create `src/index.ts` with some ts code
- update `tsconfig.json`
```json
{
    ...
    "declaration": true,                   /* Generates corresponding '.d.ts' file. */
    "outDir": "./build",                        /* Redirect output structure to the directory. */
    ...
}
```

- update `package.json` scripts to be sure to clean the `build` directory
```json
{
    ...
    "scripts": {
        "clean": "del .build/*",
        "build": "npm run clean && tsc"
    },
    ...
}
```

- make sure to gitignore `build/`

- fill `main`, `types` and `files` in `package.json`
```json
{
  ...  
  "main": "./build/index.js",
  "types": "./build/index.d.ts",
  "files": [
    "./build/**/*"
  ],
  ...
}
``` 

