# Renovate Bot Configuration

This repository contains [presets] for the [Renovate] dependency update bot, which you can easily apply to your repository to setup automatic updates.

## Usage

If you've received the Renovate [Onboarding PR], go ahead and merge it. Otherwise, create a `renovate.json` file in the root of your repository.

You can use the presets in this repository by adding them to your `renovate.json`. For example, to use the `exceptMajor` preset, which will automerge all non-major dependencies and only create PRs early on Monday mornings:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["nuhs-projects/renovate-config:exceptMajor"]
}
```

See all settings [here][renovate-settings].

It's also suggested you add the following pre-commit check, to make sure your Renovate configuration follows the schema:

```yml
repos:
  - repo: https://github.com/python-jsonschema/check-jsonschema
    rev: 0.29.4
    hooks:
      - id: check-renovate
```

[presets]: https://docs.renovatebot.com/key-concepts/presets/
[Renovate]: https://docs.renovatebot.com/
[Onboarding PR]: https://docs.renovatebot.com/getting-started/installing-onboarding/#repository-onboarding
[renovate-settings]: https://docs.renovatebot.com/configuration-options/