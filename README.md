# Silverbackltd Build Workflow

Automatically generate dockerfiles (unless already committed), build docker images and push those images to a configured container registry like GHCR

## Outputs

### `build_images`
The images that are built and pushed by the workflow

## Example Usage

To push to a ghcr registry:
```
steps:
  - name: Build Image
    uses: SilverbackLtd/build-action@v1
    with:
        push: true
        registry: ghcr.io
        username: ${{ github.actor }}
        password: ${{ secrets.GITHUB_TOKEN }}
```

To push with a different tag:
```
steps:
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
steps:
  - name: Build Image
    uses: SilverbackLtd/build-action@v1
```
