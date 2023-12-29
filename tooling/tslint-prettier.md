# Integrating TSLint and Prettier in TypeScript Projects

[TSLint](https://palantir.github.io/tslint/) and [Prettier](https://prettier.io/) are popular tools in the TypeScript ecosystem for linting and code formatting. Combining them can provide a powerful setup for maintaining clean and consistent code in your projects.

## Installing Dependencies

First, you need to install the necessary dependencies:

```bash
# Install TSLint and related packages
npm install tslint tslint-config-prettier tslint-plugin-prettier --save-dev

# Install Prettier
npm install prettier --save-dev
```

## Configuring TSLint

Create a `tslint.json` file in the root of your project with the following configuration:

```json
{
  "extends": ["tslint:recommended", "tslint-config-prettier"],
  "rules": {
    "prettier": true
  },
  "plugins": ["tslint-plugin-prettier"]
}
```

In this configuration:
- `"extends"`: Extends TSLint recommended rules and disables rules conflicting with Prettier.
- `"rules.prettier"`: Enables the Prettier rule.

## Configuring Prettier

Create a `.prettierrc` file in the root of your project with your Prettier configuration:

```json
{
  "singleQuote": true,
  "semi": false,
  "tabWidth": 2,
  "printWidth": 80
}
```

Adjust these settings according to your preferences.

## Running TSLint and Prettier

Add scripts to your `package.json` to run TSLint and Prettier:

```json
"scripts": {
  "lint": "tslint -p tsconfig.json",
  "lint:fix": "tslint -p tsconfig.json --fix",
  "format": "prettier --write \"src/**/*.ts\""
}
```

- `npm run lint`: Runs TSLint to check for linting issues.
- `npm run lint:fix`: Runs TSLint with the `--fix` option to automatically fix fixable issues.
- `npm run format`: Runs Prettier to format TypeScript files in the `src` directory.

## Integrating with Your IDE

Consider integrating TSLint and Prettier with your code editor. Most editors have extensions or plugins available for seamless integration.

- **Visual Studio Code**: Install the "TSLint" and "Prettier - Code formatter" extensions.

## Automated Formatting with Husky and lint-staged

For automating linting and formatting on pre-commit, you can use [Husky](https://typicode.github.io/husky/) and [lint-staged](https://github.com/okonet/lint-staged).

```bash
npm install husky lint-staged --save-dev
```

Then, update your `package.json`:

```json
"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
},
"lint-staged": {
  "*.ts": ["npm run lint:fix", "git add"]
}
```

This setup ensures that code is automatically formatted and linted before each commit.

Integrating TSLint and Prettier helps maintain consistent and clean code in your TypeScript projects. Customize the configurations based on your team's coding standards and preferences.

