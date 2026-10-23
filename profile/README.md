<p align="center"><img src="https://raw.githubusercontent.com/modules4cf/.github/main/assets/modules4cf-logo.png" alt="modules4cf" width="260"></p>

# modules4cf

**Community-maintained CFML modules that work on every CFML engine.**
*An open-source ForgeBox corner from the people, for the people.*

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#-get-involved)

---

## 👋 Why this organization exists

The CFML ecosystem has a wealth of great modules on [ForgeBox](https://www.forgebox.io). Over time, some of them are removed or drop support for one or more CFML engines, such as Lucee. There are good reasons for that: maintaining a module across several engines takes time and resources, and every maintainer has to set priorities.

But the applications built on these modules keep running, and their developers still need them.

**modules4cf** picks up where they left off. We take modules that are open source but are no longer available or supported for some CFML engines, and we maintain them together as a community so they keep working on **all** CFML engines.

We stand on the shoulders of the original authors. Their work, license and credit stay front and center in every project here. We are not competing with anyone. We are continuing their work so that every CFML developer can keep using it, whatever engine they run.

## 📦 Modules

| Module | Based on | Description | Engines tested in CI | ForgeBox |
|---|---|---|---|---|
| [orm4cf](https://github.com/modules4cf/orm4cf) | [cborm](https://github.com/coldbox-modules/cborm) 5.x by Ortus Solutions | Enhances the Hibernate ORM on CFML engines: service layers, Active Record, criteria queries, dynamic finders and more | Lucee 6, Lucee 7, Adobe ColdFusion 2023, Adobe ColdFusion 2025 | coming soon |

More modules are on the way. [Tell us which one you need](#-request-a-module).

## 🏷️ The `*4cf` naming convention

Every module in this organization is published under a name ending in **`4cf`** ("for CFML"), for example `orm4cf`.

* The suffix makes it clear that this is the community-maintained, cross-engine edition.
* It avoids any clash with the original package name on ForgeBox.
* If you know the original module, you can find ours by adding `4cf`.

## 🚀 Installation

Our modules are installed with [CommandBox](https://www.ortussolutions.com/products/commandbox), the CLI and package manager for CFML.

### From ForgeBox (preferred)

When a module is published on ForgeBox, install it by its slug:

```bash
box install orm4cf
```

Or add it to your `box.json`:

```json
{
    "dependencies": {
        "orm4cf": "^5.2.0"
    }
}
```

### Directly from GitHub (when it isn't on ForgeBox yet)

If a module isn't available on ForgeBox under its `*4cf` name yet, you can install it straight from GitHub. CommandBox supports this out of the box ([Git endpoint docs](https://commandbox.ortusbooks.com/package-management/code-endpoints/git)):

```bash
# Latest code from the default branch (GitHub shortcut)
box install modules4cf/orm4cf

# A specific tag, branch or commit
box install git+https://github.com/modules4cf/orm4cf.git#v5.2.0
```

You can also install a release zip from [GitHub Releases](https://github.com/modules4cf/orm4cf/releases) ([HTTP(S) endpoint docs](https://commandbox.ortusbooks.com/package-management/code-endpoints/http-s)):

```bash
box install https://github.com/modules4cf/orm4cf/releases/download/v5.2.0/orm4cf-5.2.0.zip
```

The same endpoints work as `box.json` dependencies:

```json
{
    "dependencies": {
        "orm4cf": "git+https://github.com/modules4cf/orm4cf.git#v5.2.0"
    }
}
```

> 💡 For reproducible builds, pin a tag or a release zip instead of a branch.

Each module's README lists its requirements and any setup steps specific to that module.

## 🧰 What are ForgeBox and CommandBox?

* **[ForgeBox](https://www.forgebox.io)** is the package registry for the CFML community, run by Ortus Solutions. Anyone can browse and install packages for free.
* **[CommandBox](https://www.ortussolutions.com/products/commandbox)** is the CFML command-line tool, package manager and embedded server. It installs packages from ForgeBox, Git, HTTP(S) and other [code endpoints](https://commandbox.ortusbooks.com/package-management/code-endpoints).
  * [Installing CommandBox](https://commandbox.ortusbooks.com/setup/installation)
  * [Installing packages](https://commandbox.ortusbooks.com/package-management/installing-packages)

Both are maintained by [Ortus Solutions](https://www.ortussolutions.com). Thank you to them for these tools.

## 🤖 AI assistants and skills

Using an AI coding assistant? We publish **skill files**: short, structured instructions in the open [Agent Skills](https://agentskills.io) format (`SKILL.md`) that tell an assistant how our modules really work, so it gives you correct install steps and API answers instead of guessing from outdated docs.

* **[modules4cf skill](https://github.com/modules4cf/.github/blob/main/skills/modules4cf/SKILL.md)**: the org, the `*4cf` naming and how to install our modules.
  Raw URL: `https://raw.githubusercontent.com/modules4cf/.github/main/skills/modules4cf/SKILL.md`
* **[orm4cf skill](https://github.com/modules4cf/orm4cf/blob/main/skills/orm4cf/SKILL.md)**: services, Active Record, criteria queries and migrating from cborm.
  Raw URL: `https://raw.githubusercontent.com/modules4cf/orm4cf/main/skills/orm4cf/SKILL.md`

To use one, point your assistant at the raw URL, or copy the skill folder (for example `skills/orm4cf/`) into your project's or your assistant's skills folder. Spotted something wrong in a skill? Issues and PRs are welcome, just like for code.

## 🤝 Get involved

**This is the heart of modules4cf. It is a project of the CFML community, and it only works if we all build it together.**

You don't have to be a core developer or an expert to help. You are welcome here whether you:

* use one of our modules and can report what works and what doesn't on your engine,
* found a bug or have a fix,
* can write a test, improve the docs or answer a question,
* depend on a module that lost support for your engine and want to bring it here,
* or just want to give back to the CFML community.

Every issue, test, review and pull request counts. Let's build a ForgeBox corner that belongs to all of us: from the people, for the people.

### 🐛 Report an issue

Open an issue in the module's repository, for example [orm4cf issues](https://github.com/modules4cf/orm4cf/issues). Please include:

* the CFML engine and version (for example Lucee 7.0.x or Adobe ColdFusion 2025),
* the module version,
* steps to reproduce, ideally a small code sample,
* what you expected and what happened instead.

### 📬 Request a module

Is there a ForgeBox module that was removed, or that dropped support for your engine, and that you'd like to see here? Open an issue and tell us:

* the original module and its source repository,
* its license (it must be open source and allow forks, such as Apache 2.0 or MIT),
* which engine(s) lost support and what breaks,
* whether you'd be willing to help maintain it. Co-maintainers are very welcome!

### 🛠️ Contribute code

1. **Fork** the module repository and create a branch.
2. Make **one concern per pull request**. Small, focused PRs are easier to review and merge.
3. **Add or update tests** for your change. Tests must never be skipped, weakened, or made to swallow errors to get a green build.
4. Make sure the CI matrix passes on all supported engines.
5. Open a **pull request** with a clear description, and link the related issue.

Each repository may have its own `CONTRIBUTING.md` with build and test details. Please read it before you start.

### ⚖️ License and credit

* Modules keep the license of the original project. Most are [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
* Every module **always references the original project and its authors** in its README and `NOTICE` file. Original copyright notices are never removed.
* By contributing, you agree that your contribution is licensed under the same license as the module.
* Trademarks such as ColdBox and cborm belong to their owners and are used for attribution only. modules4cf is not affiliated with, sponsored by or endorsed by Ortus Solutions, Corp.

## 🌱 How we work

* **Open by default.** Discussions, decisions and roadmaps happen in public issues and pull requests.
* **Cross-engine first.** A change is only done when it works on all the engines a module supports.
* **Respect upstream.** We credit the original authors and stay compatible with the original APIs where we can. Where it makes sense, we're happy to contribute improvements back upstream.
* **Kind and constructive.** Assume good intentions, be patient with each other, and help newcomers find their way.
* **Shared ownership.** Active contributors are invited to become maintainers. The more people share the work, the healthier the modules stay.

## 💬 Community

* [Lucee Dev Forum](https://dev.lucee.org): questions and discussions about Lucee
* [CFML Slack](https://cfml.slack.com): chat with the wider CFML community
* [GitHub issues](https://github.com/modules4cf/orm4cf/issues): bugs, ideas and module requests

---

<sub>Made with ❤️ by the CFML community. Thank you to the original authors whose work makes all of this possible.</sub>
