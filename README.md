# [ajna-by-example](https://ajna-by-example.org)

Solidity snippets for all things Ajna

*largely inspired by [solidity-by-example](https://solidity-by-example.org) & [v4-by-example](https://www.v4-by-example.org/)*

---

### License

[MIT License](LICENSE)

---

# Contributing Guide

The project is welcoming all contributions. Please try to limit PRs to:

1. Minimally opinonated examples that showcase v4 features
2. Syncing existing snippets with the latest v4 changes

## Setup

Requires [node 18](https://nodejs.org/en/download)

```bash
git clone git@github.com:ajna-finance/ajna-by-example.git

npm i
npm start
```

## Creating a new page

```bash
cp -r src/template src/pages/<path>/<name>
```

Edit the following files
* `src/pages/<path>/<name>/index.md`
* `src/pages/<path>/<name>/Template.sol`

> Please write foundry tests in `forge-test/` for your `.sol` files!

Register the page on [nav.ts](src/nav.ts)
```typescript
{
  path: "<name>",
  title: "TITLE"
}
```

Generate react, register routes, and rebuild search index
```bash
npm run generate
```
Update the [changelog](src/pages/index.tsx#L11)


## Deploying (done by admin)

Once PR is merged into `main` branch admin will need to run:

```bash
npm run deploy
```
on their local machine. This will update the `gh-pages` branch with latest changes.

PS: Sometimes the url `ajna-by-example.org` will need to be updated in the github page settings after a redeployment.