# Reload stylelint in Drupal 9

An example of Stylelint usage in a Reload Drupal context.

Included is a vanilla CSS example and a bit more advanced SCSS example.

The SCSS configuration also supports CSS which is examplified through `simple.css`.

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
