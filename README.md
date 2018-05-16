# lurkd

Following is the lurkd CLI client.

### What is this?

```bash
$ lurkd
Usage: lurkd <command> [args]

Commands:
    register   Register a provider listener and broadcaster
    list       List all registered listeners for logged in user
    remove     Remove a provider listener and broadcaster
    login      Login to a lurkd server
    logout     Logout of the current lurkd server
```

The heart and soul of lurkd is the `register` command. Let's say you want to
broadcast all new versions of npm's redis to a Slack channel so your team
can be aware of updates as soon as they drop.

```bash
lurkd register npm.redis slack

# Follow the command prompt to input slack channel URL.
```

Now, let's say you only care about either major or minor updates and you'd
rather receive an email.

```bash
lurkd register --only-minor npm.redis email

# Follow command prompt to input email.
```

### Providers

To request a new provider please submit an issue.

Provider | Command Name
--- | ---
NPM | npm
Go | go
Docker | docker
Packagist | packagist
Cargo | cargo
RubyGem | gem
PyPi | pypi

### Broadcast Transmitters

Transmitters allow you to connect an output for the notification.

Service | Command Name | Description
--- | --- | ---
Email | email | Prompts for an email to send to
Slack | slack | Prompts for an incoming webhook channel to post to
GitHub | github | Prompts for gitlab project authentication
GitLab | gitlab | Prompts for github project authentication
