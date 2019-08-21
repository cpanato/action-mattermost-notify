## Mattermost Actions

[GitHub Actions](https://github.com/features/actions) for automating builds, deployments, and so on.

- [Mattermost](https://mattermost.com) — Send Mattermost messages. Fork/inspired from https://github.com/apex/actions/tree/master/slack


You need generate a `mattermost.json` file in a step before.
For the message format you can check the [Mattermost documentation](https://docs.mattermost.com/developer/webhooks-incoming.html)

Also you can check the files for example:

 - [Simple message](./mattermost_simple.json)

## Environment Variables

Variable                            | Default                | Purpose
---------------                     |------------------------|-----------------------------------------------------------------------
MATTERMOST_WEBHOOK_URL (Mandatory)  | ` `                    | The Mattermost Incoming Webhook
MATTERMOST_CHANNEL                  | ` `                    | The name of the channel you want to post, by default will post in the channel that was setup in the webhook creation
MATTERMOST_USERNAME                 | ` `                    | The name of the sender of the message. ie, "GitHubAction"
MATTERMOST_ICON                     | ` `                    | User/Bot icon shown with Mattermost message

You can see the action block with some variables as below:

```bash
action "Mattermost Notification" {
  uses = "cpanato/action-mattermost-notify@master"
  env = {
    MATTERMOST_CHANNEL = "ci",
    MATTERMOST_USERNAME = "GitHubAction",
  }
  secrets = ["MATTERMOST_WEBHOOK_URL"]
}
```
