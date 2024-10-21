# silverbackltd-build
SilverbackLTD Build workflow will automatically generate dockerfiles, build docker images and push those images to ghcr.

## Outputs

### `build_images`
The images that are built and pushed by the workflow

## Example Usage
```
steps:
  - name: silverback-build-push
    uses: SilverbackLtd/silverbackltd-build@v3
    
```
