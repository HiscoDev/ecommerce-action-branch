# Branch naming rules
<img alt="GitHub Actions status" src="https://github.com/HiscoDev/ecommerce-action-branch/workflows/main/badge.svg">

Github action to enforce naming convention on branch names

## Usage

See [action.yml](./action.yml)

```yaml
name: 'Assert Branch Naming Convention'
on: pull_request

jobs:
  branch-naming-rules:
    runs-on: ubuntu-latest
    steps:
      - uses: HiscoDev/ecommerce-action-branch@master
        with:
          regex: '([a-z])+\/([a-z])+' # Regex the branch should match. This example enforces grouping
          allowed_prefixes: 'feature,stable,fix' # All branches should start with the given prefix
          ignore: master,develop # Ignore exactly matching branch names from convention
          min_length: 5 # Min length of the branch name
          max_length: 20 # Max length of the branch name
```

## License
The scripts and documentation in this project are released under the [MIT License](./LICENSE)
