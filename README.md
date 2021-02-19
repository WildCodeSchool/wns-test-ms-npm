# Publish a npm package

## Steps

- initialize a new npm project
```shell
npm init -y
```

- change the name in package.json to @organization/project
- initialize git repository and commit
- publish your package

```shell
npm login
npm publish --access public
```

- check your profile on https://www.npmjs.com/