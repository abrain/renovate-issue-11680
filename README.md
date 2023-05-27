# Reproduction of Renovate bot issue 11680

As stated in the [bug report](https://github.com/renovatebot/renovate/issues/11680) Renovate opens more than one Pull Request for pinning the dependencies.

In this repo it seems to be caused by the group presets `group:jsTest` (part of the repo config) and `group:socketio` (included via `group:recommended`).

## Environment

Renovate runs in a self-hosted setup, using the `renovate/renovate` Docker image.
At the time of writing the used version is `35.102.6`.

The global `config.js` makes no other changes to the behaviour:

```
module.exports = {
  autodiscover: false,
  platform: 'github',
  repositories: [
    <some other repos>,
    'abrain/renovate-issue-11680'
  ],
  token: 'REDACTED'
};
```
