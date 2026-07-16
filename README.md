
## Soft fork of Obsidian Gistr

This is a soft fork of Gistr, patching two points.

### 1. CSP security errors in Obsidian with Opengist < v1.13.x

This plugin behaves differently for Opengist and GitHub embedds. For Opengist, the stylesheet for your embeddings is included twice.
Once as inline style code and once as link to the external stylesheet on your Opengist server.

Loading external stylesheets is prohibited because by the default Obsidian CSP setting (after all it is an Electron app).

This results in a lot of errors depending how many files you embed. Check the Developer Console (`CTRL + I`) in Obsidian for details.

Patch 1 removes the link to the remote stylesheet and inlines the CSS just like how GitHub is implemented right now.

### 2. Plugin broken since Opengist 1.13

As the author of Opengist feared, the new structure of the delivered embed files has broken the plugin entirely.

Patch 2 aims to fix the plugin for the new Opengist version.


The following is a short excerpt from the main documentation. For the full sermon, check the README on the upstream repository.

***

## Gistr

> A plugin for Obsidian.md which allows you to create, convert, and update notes from Obsidian to Github or Opengist. As well as integrate fully functional websites into your notes.


**Supported Services**:
- [Github Gists](https://gist.github.com)
- [OpenGist Server](https://github.com/thomiceli/opengist)
- _As of v1.6.x_: Any website

## Features
This section gives a brief explanation of what Gistr can do. Please note that the list below is very minimal and does not cover everything the plugin can do. To view a full feature list; read the documentation:

- [Docs: Basic Usage](https://aetherinox.github.io/obsidian-gistr/usage/basic/)
- [Docs: Properties List](https://aetherinox.github.io/obsidian-gistr/usage/properties/)

## Methods:
As of version `1.6.0`, Gistr now includes **two** ways to integrate gists into your obsidian.md notes.

- Method 1: [Codeblocks](#method-1-codeblock)
- Method 2: [Integrated Browser](#method-2-integrated-browser)

## Install (BRAT Plugin Manager)

Plugin can also be installed utilizing the [BRAT](https://github.com/TfTHacker/obsidian42-brat) plugin.
- Install [BRAT](https://github.com/TfTHacker/obsidian42-brat) using the Obsidian Plugin manager
- In your Obsidian settings on the left, select **BRAT** in the list.
- In BRAT settings, click the button **Add Beta Plugin**
- In the textbox, supply the URL to this repo
  - `https://github.com/Aetherinox/obsidian-gistr`
- Once Gistr is installed, activate it in your Obsidian settings. <img src="https://github.com/Aetherinox/obsidian-gistr/assets/118329232/3e512f8a-5c7d-4bff-a3e8-3ef88e673e72" data-canonical-src="https://github.com/Aetherinox/obsidian-gistr/assets/118329232/3e512f8a-5c7d-4bff-a3e8-3ef88e673e72" height=20px />


## Build
Instructions for building various aspects of Gistr:

### Gistr
For a detailed set of instructions on how to download this plugin's source files and compile your own version, check out the wiki link below:
- [How to Build Gistr](https://aetherinox.github.io/obsidian-gistr/advanced/build/)


## Shoutouts
- [thomiceli](https://github.com/thomiceli)  over at [OpenGist](https://github.com/thomiceli/opengist) for implementing the JSON functionality request.
- [linjunpop](https://github.com/linjunpop) for developing the first Obsidian [Gist](https://github.com/linjunpop/obsidian-gist) plugin. It was a top choice in my list of plugins used.

