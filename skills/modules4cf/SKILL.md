---
name: modules4cf
description: >
  Explains the modules4cf GitHub organization: community-maintained, cross-engine continuations of
  CFML/ColdBox modules that were removed from ForgeBox or dropped support for an engine such as Lucee,
  published under names ending in "4cf" (for example orm4cf, the continuation of cborm). Use this skill
  when the user asks about modules4cf, any "*4cf" package, finding a cross-engine replacement for a
  ColdBox module, installing a modules4cf module with CommandBox (from ForgeBox or straight from GitHub),
  or reporting issues and contributing. Hand off to the module's own skill (for example orm4cf) for API questions.
license: Apache-2.0
metadata:
  homepage: https://github.com/modules4cf
---

# modules4cf

## What it is

[modules4cf](https://github.com/modules4cf) is a community-run GitHub organization that maintains
open-source CFML modules that are no longer available, or no longer supported on some CFML engines,
so they keep working on **all** CFML engines. Every module keeps the original license (mostly
Apache 2.0) and credits the original project and authors in its README and `NOTICE`.

modules4cf is not affiliated with, sponsored by or endorsed by Ortus Solutions, Corp. ColdBox and
cborm are Ortus trademarks and are only used for attribution.

## The `*4cf` naming convention

Every module is published under the original name plus the suffix **`4cf`** ("for CFML"):

- it marks the community-maintained, cross-engine edition,
- it never clashes with the original package name on ForgeBox,
- if you know the original module, add `4cf` to find ours.

## Repositories

| Repository | Kind | Based on | Status |
|---|---|---|---|
| [orm4cf](https://github.com/modules4cf/orm4cf) | Module | [cborm](https://github.com/coldbox-modules/cborm) 5.1.0 by Ortus Solutions | Active. CI: Lucee 6, Lucee 7, Adobe ColdFusion 2023, Adobe ColdFusion 2025 |
| [registry](https://github.com/modules4cf/registry) | Not a module | - | Planned self-hostable, ForgeBox-compatible package registry for modules4cf.org |
| [.github](https://github.com/modules4cf/.github) | Not a module | - | Org profile and this skill |

Always check `https://github.com/modules4cf` for the current list before telling a user a module
does not exist.

## Installing a module

Modules are installed with [CommandBox](https://commandbox.ortusbooks.com/).

### Current status (read this first)

- **Not on ForgeBox yet.** No modules4cf module is published on ForgeBox yet, so `box install orm4cf`
  does not work today. It will once the module is published.
- **No modules4cf release tags yet.** orm4cf has not had its first release (the planned first one is
  `v5.2.0`), so there are no release zips and no `#v5.2.0` tag yet. orm4cf still carries the tags it
  inherited from cborm (`v5.1.0` and older, `v6.0.0-beta.*`). These point to the original cborm code,
  **without** the cross-engine fixes. Don't pin them.
- Until the first release, install from the default branch: `box install modules4cf/orm4cf`.

### From GitHub (works today)

```bash
# Latest code from the default branch (GitHub shortcut)
box install modules4cf/orm4cf

# A specific tag, branch or commit (once release tags exist)
box install git+https://github.com/modules4cf/orm4cf.git#v5.2.0

# A release zip from GitHub Releases (once releases exist):
# copy the zip's URL from https://github.com/modules4cf/orm4cf/releases
box install <zip URL from the release page>
```

The same endpoints work as `box.json` dependencies:

```json
{
    "dependencies": {
        "orm4cf": "git+https://github.com/modules4cf/orm4cf.git#v5.2.0"
    }
}
```

CommandBox installs the module into `modules/<slug>/`, for example `modules/orm4cf/`. For
reproducible builds, pin a tag or release zip instead of a branch.

### From ForgeBox (once published)

```bash
box install orm4cf
```

```json
{
    "dependencies": {
        "orm4cf": "^5.2.0"
    }
}
```

Docs: [Git endpoint](https://commandbox.ortusbooks.com/package-management/code-endpoints/git),
[HTTP(S) endpoint](https://commandbox.ortusbooks.com/package-management/code-endpoints/http-s),
[installing packages](https://commandbox.ortusbooks.com/package-management/installing-packages).

## modules4cf.org registry (planned)

A self-hostable, ForgeBox-compatible registry is planned in
[modules4cf/registry](https://github.com/modules4cf/registry). The goal is that CommandBox users can
register `modules4cf.org` as a package endpoint instead of, or next to, ForgeBox. It is **not
available yet**. Don't give users endpoint configuration for it; point them to the repository instead.

## Module skills

Each module can ship its own skill with API details. Use it for anything beyond installation:

- **orm4cf** (cborm 5.x API, Hibernate ORM services, Active Record, criteria queries):
  `https://raw.githubusercontent.com/modules4cf/orm4cf/main/skills/orm4cf/SKILL.md`
  (until that skill is merged, use the orm4cf [readme](https://github.com/modules4cf/orm4cf#readme)
  and the [cborm docs](https://coldbox-orm.ortusbooks.com/), whose API is the same)

## Reporting issues and contributing

- **Bugs and ideas:** open an issue in the module's repository, for example
  [orm4cf issues](https://github.com/modules4cf/orm4cf/issues). Include the engine and version,
  the module version, steps to reproduce (ideally a small code sample), and expected vs actual result.
- **Module requests:** open an issue with the original module and its source repository, its license
  (must be open source and allow forks, such as Apache 2.0 or MIT), which engines lost support and
  what breaks, and whether you can help maintain it.
- **Pull requests:** fork, branch, one concern per PR, add or update tests, make the CI matrix pass
  on all supported engines. Tests must never be skipped, weakened or made to swallow errors.
  Read the repository's `CONTRIBUTING.md` first.
- **Questions:** [Lucee Dev Forum](https://dev.lucee.org) or the [CFML Slack](https://cfml.slack.com).

## Rules for answering

- Don't claim a module is on ForgeBox, or that a release tag exists, without checking
  `https://github.com/modules4cf/<module>/releases` or `https://www.forgebox.io/view/<module>`.
- Don't invent modules. If a user needs one that isn't listed, suggest opening a module request.
- Keep credit to the original project when describing a module.
