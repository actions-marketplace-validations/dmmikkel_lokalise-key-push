# lokalise-key-push
GitHub Action that pushes new translations keys to Lokalise

## How to use
```
name: Push keys to Lokalise

on:
  push:
    branches:
      - master
    paths:
     - 'src/main/resources/*.properties'

jobs:
  upload:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3.0
    - uses: dmmikkel/lokalise-key-push@Add-support-for-multiple-formats
      with:
        api-token: ${{ secrets.lokalise_token }}
        project-id: 748610715d8afa5681a4b1.23888602
        directory: src/main/resources
        format: properties # json or properties
        platform: web
        filename: messages_%LANG_ISO%.properties

```