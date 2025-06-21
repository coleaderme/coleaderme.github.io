+++
title = "Zola deploy"
date = "2024-03-16"
description = "zola github pages build and deploy"
[extra]
cover_image = "images/gh-pages.webp"
+++

# After so many trial and errors..  

Make changes to your-name.github.io repo's  
1.  **Actions** >> **New Workflow** >>  

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

2. **Settings** >> **pages** >>  
{%admonition(type="info")%}
See cover image
{%end%}
