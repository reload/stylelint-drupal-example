# Reload stylelint in Drupal 9

An example of Stylelint usage in a Reload Drupal context.
Included is a vanilla CSS example, a bit more advanced SCSS example and an example of project root level configuration.
The included github actions is also representative of what would be desired from a project in regards to automation.
The SCSS configuration also supports CSS which is examplified through `simple.css`.

## Required for getting a style linting setup running in your project.

- [stylelint](https://www.npmjs.com/package/stylelint) - Static analysis of style definition.
- [@reloaddk/stylelint-recommended](https://www.npmjs.com/package/@reloaddk/stylelint-recommended) - Common opinions about well defined CSS code and therefore code quality.
- [@reloaddk/stylelint-recommended-scss](https://www.npmjs.com/package/@reloaddk/stylelint-recommended-scss) - Common opinions about well defined CSS and SCSS code and therefore code quality.
- [prettier](https://www.npmjs.com/package/prettier) - Code style.

```
npm install stylelint @reloaddk/stylelint-recommended prettier --save-dev
```


## Getting up and running

### Install Drupal
Get the Drupal site up and running.
This can be done using [Task](https://taskfile.dev/#/) and [Lando](https://lando.dev).

```
task up
```

### Destroy

```
task reset
```

### Usage

Stylelint is used for code quality where as prettier is used for code style.
The `@reloaddk/stylelint-recommended` packages have no code style opinions and
relegate that responsability to the project in the form of prettier, additional
added stylelint configs or rules.

The commands below only apply for the non-scss example theme.

#### Linting

The `clean.css` shows an example of what is being checked. `notacolor` is not
faulty CSS and therefore not something that is neither checked nor fixable. 

```
task lint
```

#### Formatting

Some things can be auto fixed in `error.css` but some things like
`Do not use empty rulesets` is not auto-fixable.

```
task fmt
```
