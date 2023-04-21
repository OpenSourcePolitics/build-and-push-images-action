# Build and push images action

Allows to build and push Docker images to a Docker registry.

## Inputs
- registry:
  - description: 'Registry url'
  - required: true
- namespace:
  - description: 'Namespace'
  - required: true
- password:
  - description: 'Password'
  - required: true
- username:
  - description: 'Username'
  - required: false
  - default: "userdoesnotmatter"
- image_name:
  - description: 'Image name'
  - required: true
- tag:
  - description: 'Image tags'
  - required: true
- push:
  - description: 'Push image to registry'
  - required: true
    - default: "true"

## Usage 
```yaml
- name: Build and push Docker image
  uses: OpenSourcePolitics/build-and-push-images-action@v1
  with:
    registry: ${{ secrets.REGISTRY_URL }}
    namespace: ${{ secrets.REGISTRY_NAMESPACE }}
    password: ${{ secrets.REGISTRY_PASSWORD }}
    username: ${{ secrets.REGISTRY_USERNAME }}
    image_name: ${{ secrets.REGISTRY_IMAGE_NAME }}
    tag: ${{ github.ref }}
    push: "true"
```