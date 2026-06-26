# Smart Home YVR

Public repository for the smart-home-yvr Home Assistant add-on metadata.

## Home Assistant add-on repository layout

- repository.yaml: Home Assistant repository manifest.
- smart-home-yvr/config.yaml: Add-on manifest and options schema.
- smart-home-yvr/DOCS.md: Add-on usage and setup docs shown in Home Assistant.
- smart-home-yvr/README.md: Add-on directory overview.
- CHANGELOG.md: Repository-wide change history.

## API source and CI/CD

The NestJS API source and container build pipeline are in this monorepo at apps/smart-home-yvr.

This app directory keeps only Home Assistant repository/add-on metadata:
- repository.yaml
- smart-home-yvr/config.yaml
- smart-home-yvr/DOCS.md

## Add this repository to Home Assistant

1. In Home Assistant, go to Settings -> Add-ons -> Add-on Store.
2. Open the three-dot menu and select Repositories.
3. Add the final URL where repository.yaml is hosted.

## Local metadata validation

The bnb GitHub workflow validates apps/ha-addons/repository.yaml and apps/ha-addons/smart-home-yvr/config.yaml syntax and required fields.
