# Silverbackltd Build Workflow

Automatically generate dockerfiles (unless already committed), build docker images and push those images to a configured container registry like GHCR

## Outputs

### `build_images`
The images that are built and pushed by the workflow

## Example Usage

To push to a ghcr registry:
```
jobs:
  your-action:
    name: Run action
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
      id-token: write
    steps:
      - uses: actions/checkout@v4

      - name: Build Image
        uses: SilverbackLtd/build-action@v1
        with:
            push: true
            tag: v1.0.0
            registry: ghcr.io
            username: ${{ github.actor }}
            password: ${{ secrets.GITHUB_TOKEN }}
```

To push with a different tag:
```
jobs:
  your-action:
    name: Run action
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
      id-token: write
    steps:
      - uses: actions/checkout@v4

      - name: Build Image
        uses: SilverbackLtd/build-action@v1
        with:
            push: true
            tag: v1.0.0
            registry: ghcr.io
            username: ${{ github.actor }}
            password: ${{ secrets.GITHUB_TOKEN }}
```

To just test the build:
```
jobs:
  your-action:
    name: Run action
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:

      - uses: actions/checkout@v4

      - name: Build Image
        uses: SilverbackLtd/build-action@v1
```
