+++
title = "zola-deploy"
date = "2024-03-16"
description = "zola github pages build and deploy"
+++

# After so many trial and errors..  

Make changes to your-name.github.io repo's  

**Actions** >> **New Workflow** >>  

PASTE this.  
```yaml
name: Zola on GitHub Pages

on: 
 push:
  branches:
   - main

jobs:
  build:
    name: Publish site
    runs-on: ubuntu-latest
    steps:
    - name: Checkout main
      uses: actions/checkout@v4
    - name: Build and deploy
      uses: shalzz/zola-deploy-action@v0.18.0
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

*Important*  **Settings** >> **pages** >>  

![Settings Page](https://github.com/coleaderme/coleaderme.github.io/blob/main/static/images/gh-pages.png)  

Done!