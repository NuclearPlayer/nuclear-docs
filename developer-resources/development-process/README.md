---
description: How to run Nuclear in development mode and start coding
---

# Development process

## Prerequisites

Ensure that you have installed the prerequisites:

* Node.js LTS (20)
* npm v10
* git
* Rust - How to install: [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)
* Your platform's build tools required to recompile native dependencies.
  * Node-gyp is the tool we use to recompile them. It will be installed automatically, but you need to install its dependencies yourself. Check how to do it here: [https://github.com/nodejs/node-gyp#installation](https://github.com/nodejs/node-gyp#installation)
  * **You will not be able to run Nuclear without these dependencies.**
* Linux is recommended (but not required) for development. The process should work the same for all platforms.

## Quickstart

Start by cloning the repository:

```bash
$ git clone git@github.com:nukeop/nuclear.git
```

Go to the project root and install the dependencies:

```bash
$ cd nuclear
$ npm install
```

This will install the dependencies in the project root, and automatically link the local packages with lerna. Nuclear is using a monorepo structure, which means it's a collection of Node packages, as you can see in the `packages` folder.

{% hint style="warning" %}
You should not install the dependencies inside individual package folders. This will be done for you when you run `npm install` in project root.
{% endhint %}

Next, you can run the tests:

```bash
$ npm test
```

{% hint style="info" %}
Nuclear has CI pipelines, which means that we use Github Actions to verify that tests pass and the project can be built after every commit. You can see the status of these pipelines here: [https://github.com/nukeop/nuclear/commits/master](https://github.com/nukeop/nuclear/commits/master/)

Next to each commit, there is a checkmark or a red X. If there's a checkmark, and something doesn't work for you, it's likely that it's a problem on your machine.
{% endhint %}

Or start the program in development mode:

```bash
$ npm start
```

To build a production release, run this:

```bash
$ GITHASH=<version> npm run build:<platform>
```

Replace `<version>` with a string that will be added to the filenames of the built packages, e.g. `0.6.30` or a short githash: `f4b6771`. This only affects the filenames, but needs to be set.

Replace `<platform>` with the name of your platform: `linux`, `macos`, `windows` or `all`.

The binaries will be created in `<root>/release`.

## Troubleshooting

### Errors

{% hint style="info" %}
Here are some commonly seen errors when running the tests, the build, or the player itself. If you see anything else, let us know on Github: [https://github.com/nukeop/nuclear/issues](https://github.com/nukeop/nuclear/issues), or on Discord: [https://discord.gg/JqPjKxE](https://discord.gg/JqPjKxE)
{% endhint %}

#### ModuleNotFoundError: No module named 'distutils'

You have to install Python's setuptools, needed for `node-gyp`. You can do that by running:

`$ pip install setuptools`

#### npm ERR! Error: could not find the `cargo` executable.

This means you need to install Rust. See here how to do that: [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)

