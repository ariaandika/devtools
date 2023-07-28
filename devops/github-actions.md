# Github Actions

automate build test and deploy

- CI, Merge Code In
- CD, Release Code Out

## Continuous Integration

reserved file

```yml
# .github/workflows/integrate.yml

name: Node Continuous Integration

on:
  pull_request:
    branches: [ master ]

jobs:
  test_pull_request:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v1
        with:
          node-version: 12
      - run: npm ci
      - run: npm test
      - run: npm run build

```

## Continuous Deployment

```yml
# .github/workflows/deploy.yml

name: Node Continuous Deployment

on:
  push:
    branches: [ master ]

jobs:
  test_pull_request:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - uses: actions/setup-node@master
        with:
          node-version: 12
      - run: npm ci
      - run: npm run build
        env:
          ENV_TOKEN: ${{ secrets.ENV_TOKEN }}

# secrets can be managed in repository setting.secret
```

## Publishing

```yml
name: NPM Package

on:
  release:
    types: [created]

jobs:
  build:
  
  publish-npm:
    needs: build
  
  publish-gpr:
    needs: build
```
