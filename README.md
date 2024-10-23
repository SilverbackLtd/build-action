# Silverbackltd Build Workflow

Automatically generate dockerfiles (unless already committed), build docker images and push those images to a configured container registry like GHCR

## Outputs

### `build_images`
The images that are built and pushed by the workflow

## Example Usage
```
steps:
  - name: Build Image
    uses: SilverbackLtd/build-action@v1
    
```
