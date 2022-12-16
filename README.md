# My-Docs

## How to create a documentation repository

### References

- https://squidfunk.github.io/mkdocs-material/

### Steps

```

# create new public repository

# 

# git clone to local

pip3 install mkdocs-material
mkdocs new .

# Auto deploy using git actions

mkdir -p .github/workflows
cat << EOF > .github/workflows/ci.yml
name: ci 
on:
  push:
    branches:
      - master 
      - main
permissions:
  contents: write
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v4
        with:
          python-version: 3.x
      - run: pip install mkdocs-material 
      - run: mkdocs gh-deploy --force
EOF

```

### How to publish to GitHub pages

Settings -> Pages -> Source -> Deploy from a branch -> gh-pages -> /(root)

### How to search

https://lunrjs.com/guides/searching.html


### Force build

```
mkdocs gh-deploy --force
```

