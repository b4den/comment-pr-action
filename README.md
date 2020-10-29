# Hello world javascript action

This action prints a message on the PR its used in. 

## Inputs

### `message`

**Required** The message to write on the PR. Default `""`.


## Example usage

```
uses: b4den/comment-pr-action@master
  env:
	GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  with:
	message: "Testing message"
```
