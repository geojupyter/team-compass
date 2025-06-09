---
title: "Coding policies and practices"
---

## Checks

### Task runners

We like to use [pre-commit](https://pre-commit.com/) where possible.
It helps automate the execution of checks and autofixes so we rely less on our memories
to run tools.


### Formatting

We use auto-formatters for code format concerns, like indentation, line length, and
more.

For Python, we use [Ruff](https://docs.astral.sh/ruff/), and for JavaScript and more, we
use [Prettier](https://prettier.io/).


#### Some specifics

##### Tailing commas

We prefer to use trailing commas in any multi-line objects or lists.
Trailing commas make it easier to add or remove items from an object, and they make
diffs more readable.

```diff
 const foo = [
     "bar",
-    "baz",
-    "qux"
+    "baz"
 ];
```

We prefer to see the diff below to the diff above:

```diff
 const foo = [
     "bar",
     "baz",
-    "qux",
 ];
```


### Linting

We use linters to help make our code
more consistent ([examples](https://docs.astral.sh/ruff/rules/#pep8-naming-n)),
more clear ([examples](https://docs.astral.sh/ruff/rules/#flake8-simplify-sim)),
and to avoid common pitfalls ([examples](https://docs.astral.sh/ruff/rules/#flake8-bugbear-b)).

For Python, we use [Ruff](https://docs.astral.sh/ruff/), and for JavaScript/TypeScript,
we use [ESLint](https://eslint.org/).


### Testing

... TODO ...
