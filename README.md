# Comment on PR action

Just like [comment-on-pr](https://github.com/unsplash/comment-on-pr), but without the overhead of including a separate Docker image into your action. This reduces the overhead of bringing in `alpine-ruby` by surfacing the same logic using native JavaScript.

This action prints a message on a pull request, or push. 

## Inputs

### `message`

**Required** The message to write on the PR. Default `""`.

### `check-for-duplicates`

**Required** Checks to see if message exists before posting Default `true`.

## Example usage

```
uses: b4den/comment-pr-action@master
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  with:
    message: "Testing message"
```
