# Comment on PR Github Action

Just like [comment-on-pr](https://github.com/unsplash/comment-on-pr), but without the overhead of including a separate Docker image into your action. This version Also supports CircleCI and can be run standalone from almost anywhere.

This action prints a message on a pull request, or push event.

## Inputs

### `message`

**Required** The comment to write on the pull request.

### `check-for-duplicates`

**Optional** Checks to see if message exists before posting. Default `true`.

## Example usage

```
uses: b4den/comment-pr-action@master
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  with:
    message: "Testing message"
```

## Complete sample
```
name: comment-on-pr example
on: pull_request
jobs:
  example:
    name: sample comment
    runs-on: ubuntu-latest
    steps:
      - name: comment PR
        uses: b4den/comment-pr-action@master
          env:
            GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          with:
            message: "PR test comment."
            check-for-duplicates: false

```
## Additional use-cases

You can also use this executable directly within your CircleCI environments to post-back to Github. You'll need the following enabled in env:

1. `GITHUB_PAT`: A personal access token with appropriate repository permissions for commenting on pull requests
2. `CIRCLE_PULL_REQUEST`: A string value representing the following structure: `https://github.com/:owner/:repo/pull/:number`. This should be populated by default.


One file, two platforms, no dependencies.
