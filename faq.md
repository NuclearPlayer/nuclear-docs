---
description: Frequently asked questions
---

# FAQ

## Is there an Android/iOS version?

No. Apple's and Google's stores would **never** accept Nuclear in event the simplest possible form. Sideloading on both platforms is possible but hard for most people, and mobile phones are user-hostile platforms. \
\
While at some point we might release a mobile version with limited functionality, it's not a priority right now. I don't have a smartphone and I'm not planning to get one, so my familiarity with mobile programs and their usage patterns is poor.

Another kind of problem is posed by the fact that the libraries we use for retrieving audio streams depend on network APIs that are only available on desktop, and it would be particularly hard to reproduce their behavior on mobile phones.

## Which file do I download?

Every file contains the same version of Nuclear, there are no functional differences.

First, click "Releases":

![](<.gitbook/assets/image (10).png>)

You will see a list of releases. Find the most recent one (at the top), and click "Assets".

![](<.gitbook/assets/image (1) (1).png>)

You will see a list of files. You only need one of those files.

Here's which ones you should get on each platform, and what the differences between them are:

### **Windows:**

#### **nuclear.Setup.\<version>.exe**

This is an installer for Windows, which starts a standard installation wizard.

#### nuclear-\<version>.exe

This is a portable version, meaning the entire program is contained within a single file.

### Linux

#### Appimage

This a relatively new format that should run on most Linux distributions. It contains everything, including dependencies in a single file, and it allows the program to run in a portable way or be installed.

#### .deb

This is a package for Debian-based distros.

#### .rpm

This is a package for Red Hat/Fedora-based distros.

#### .snap

This is a universal package format that can run on most distros. In Ubuntu, this is becoming the standard format for many packages

#### **.tar.gz**

This is an archive containing compressed binary files and other assets. It should run on most distros.

### MacOS

On Mac, you should download the .dmg, .pkg, or .zip package. They should all work the same way.

## Why does it play wrong songs sometimes?

As opposed to players that maintain their own music libraries like Spotify or Deezer, Nuclear has to find music streams based on the name of the artist and the track title. This process is imperfect and can sometimes lead to wrong streams being played. Here's what you can do to mitigate it:

* Right click the track in the queue and select a different stream
* Select a different streaming source if you can't find the correct stream on the list - maybe it's not available in that source
* In the future we will add a system where you'll be able to verify streams so that this process of finding correct streams is outsourced

## Where can I find plugins?

Currently, there is no single centralized place for plugins. You can find some by searching on Github, but the plugins feature is not very popular and there aren't that many. We're working on changing that, so if you make a plugin, make sure to let us know. There is also a channel for sharing plugins on Discord.

We want to create more sample plugins in the future as examples for plugin creators to base their work on.

## Where can I suggest new features?

We have a board for that here: [https://nuclear.featureupvote.com/](https://nuclear.featureupvote.com/)

You can either propose new ones or vote on existing features.

You can also create a thread on Github: [https://github.com/nukeop/nuclear/issues/new?assignees=\&labels=feature+request\&template=feature\_request.md\&title=](https://github.com/nukeop/nuclear/issues/new?assignees=\&labels=feature+request\&template=feature\_request.md\&title=)
