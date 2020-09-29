name: Deploy
on:
  push:
    branches:
      - master

jobs:
  deploy:
    name: Deploy
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      # Build, transpile etc.
      - name: Upload static assets to Dark canvas
        uses: gregbrimble/dark-static-assets-action@v1.0.0
        with:
          user: DARK_USERNAME_HERE
          password: ${{ secrets.DARK_PASSWORD }}
          canvas: DARK_CANVAS_NAME_HERE
          paths: PATH_TO_DIRECTORY_HERE
