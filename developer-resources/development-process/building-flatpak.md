---
description: How to build Nuclear as a flatpak package
---

# Building flatpak

You can also build a flatpak version. You will need to install `gobject-introspection`, and `flatpak-builder`. After this you will need to install the runtimes and depedencies required by `flatpak-builder` for the compile process. You will need the 19.08 version of these flatpaks.

```text
$ flatpak install flathub org.freedesktop.Platform
$ flatpak install flathub org.freedesktop.Sdk
$ flatpak install flathub io.atom.electron.BaseApp
```

Next, to build the project \(use the `--verbose` flag to get more output\):

```text
$ flatpak-builder build-dir org.js.nuclear.Nuclear.json
```

To run the built app:

```text
$ flatpak-builder --run build-dir org.js.nuclear.Nuclear.json run.sh
```

You can turn the app to a local repo. Currently the file builds the latest release.

