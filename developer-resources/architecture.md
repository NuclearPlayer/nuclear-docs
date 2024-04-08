---
description: About the way the code is organized
---

# Architecture

Nuclear is structured in the form of a monorepo, in which multiple packages live in the same repository. This structure is managed by a tool called Lerna. The dependencies for all of those packages are installed together, and hoisted at the root of the project.

### Overview of the packages

#### app

This package contains the main web app displayed inside the Electron window. This is a standard React app, which includes Redux and redux-thunk for state management. It's bundled and transpiled using Webpack.

#### core

This is a library containing functionalities common to other packages, and should not be importing any of them. Plugin code as well as modules implementing communication with external APIs can be found here, as well as some domain models, a master list of settings, and various other definitions.

#### i18n

This package contains translations and scripts related to maintaining them.

#### main

This package contains the server side Electron code, which handles Electron initialization, functionalities related to the program window, and services (such as handling the tray icon, Discord rich presence, downloads, and anything else that can't be done in the web app).

#### ui

This package contains functionality-agnostic UI components, and a Storybook-based demo page for them. These components are imported and used by the `app` package to build the interface.

#### scanner

Local library scanner. This is a Rust crate compiled to a native Node module. This utility used to be written in Node, but was remade in Rust for performance gains.
