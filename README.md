# Comment on PR action

Just like [comment-on-pr](https://github.com/unsplash/comment-on-pr), but without the overhead of including a separate Docker image into your action. 

This has the added benefits of _not_ including a separate operating system runtime, no additional gems/ npm packages and is distributed as a single JavaScript file that is run natively by Github Actions. This also speeds up your action flows by reducing the need to pull a docker image into your flow, over the network, just for the sake of commenting on a PR. See [this article](https://docs.github.com/en/free-pro-team@latest/actions/creating-actions/about-actions#:~:text=For%20actions%20that%20must%20run,are%20slower%20than%20JavaScript%20actions.) for more information.

This action prints a message on a pull request, or push event. 

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
