## About

I was looking at [yq GitHub Actions](https://github.com/marketplace/actions/yq-portable-yaml-processor) but I can't see any usage examples. After some tweaks and tests, I finally made it to work. Checkout the [workflow file](.github/workflows/main.yaml) for more details.

On high level, here is how the workflow should work:

1. Developer push a commit with a tag
2. Workflow starts
    a. Update/inplace update the container image in the _deployment.yaml_ file using [yq](https://mikefarah.gitbook.io/yq/operators/assign-update)
    b. Add and commit the _deployment.yaml_ file back to this repository
3. Workflow ends

## Status

It's working

## Resources

- [yq GitHub](https://github.com/mikefarah/yq)
- [First hint I found](https://github.com/mikefarah/yq/issues/615#issuecomment-751831996)
- [Actions to commit file](https://github.com/stefanzweifel/git-auto-commit-action)
