---
description: How to run Nuclear in development mode and start coding
---

# Development process

### Prerequisites

Ensure that you have installed the prerequisites:

* Node.js v.12 \(note that v.14 **will not work** because of an incompatibility in one of the dependencies\)
* npm v.6
* git
* Your platform's build tools required to recompile native dependencies
* Linux is recommended \(but not required\) for development

### Quickstart

Start by cloning the repository:

```bash
$ git clone git@github.com:nukeop/nuclear.git
```

Go to the project root and install the dependencies:

```bash
$ cd nuclear
$ npm install
```

This will install the dependencies in the project root, then use lerna to install the dependencies of individual packages.

Next, you can run the tests:

```bash
$ npm test
```

Or start the program in development mode:

```bash
$ npm start
```

To build a production release, run this:

```bash
$ GITHASH=<version> npm run build:<platform>
```

Replace `<version>` with a string that will be added to the filenames of the built packages, e.g. `0.6.13` or a short githash: `f4b6771`. This only affects the filenames, but needs to be set.

Replace `<platform>` with the name of your platform: `linux`, `macos`, `windows` or `all`.

The binaries will be created in `<root>/release`.

