<div align="center">

# Neorg - An Organized Future


<a href="https://github.com/neovim/neovim"> ![Requires](https://img.shields.io/badge/requires-neovim%200.5%2B-green?style=flat-square&logo=neovim) </a>
<a href="https://discord.gg/T6EgTAX7ht"> ![Discord](https://img.shields.io/badge/discord-join-7289da?style=flat-square&logo=discord) </a>
<a href="https://paypal.me/ewaczupryna?locale.x=en_GB"> ![Paypal](https://img.shields.io/badge/support-paypal-blue?style=flat-square&logo=paypal) </a>
<a href="https://www.buymeacoffee.com/vhyrro"> ![BuyMeACoffee](https://img.shields.io/badge/support-buy%20me%20a%20coffee-ffdd00?style=flat-square&logo=buy-me-a-coffee) </a>
<a href="https://patreon.com/vhyrro"> ![Patreon](https://img.shields.io/badge/support-patreon-F96854?style=flat-square&logo=patreon) </a>


<a href="/LICENSE"> ![License](https://img.shields.io/badge/license-GPL%20v3-brightgreen?style=flat-square) </a>
<a href="#wip"> ![Status](https://img.shields.io/badge/status-WIP-informational?style=flat-square) </a>

</div>

---

> The pain... it won't stop. After so much oppression from other text editors, it's time we fight back.
With the introduction of lua, we *will* fight back.

---

### Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Questions about usage](#usage-questions)
- [WIP Status](#wip)
- [Check out the wiki](#consult-the-wiki)
- [Contributing](#contributing)

# Introduction
### What this project is, and what it isn't
  - This project is supposed to serve as an organizational tool for Neovim. It will run on the .norg file format - a revised, extensible and more computer friendly format compared to .org, all while retaining a decent amount of backwards compatibility with org (you will be able to convert between both formats).
  - A foundation for developers to make their own extensions to the plugin and interface with other parts of user-contibuted code, known as modules (more info below)
  - A full on competitor to emacs's org-mode
 ### What this project isn't
  - **An org-mode clone** - this project does not plan on recreating or cloning org mode in neovim. Rather, the goal of this repo is to take concepts from other organizational tools and reimagine them for the great text editor that neovim is. Expect a bit of familiarity but also a lot of changes, things tailored to the vim philosophy.

---
# Installation
## Using packer

If you don't know what you're doing, just run this:

```lua

  use { 'Vhyrro/neorg', config = function()

      require('neorg').setup {}

  end}
```

Otherwise:

```lua
  use { 'Vhyrro/neorg', config = function()
      require('neorg').setup {
        load = {
          ["your.module"] = { git_address = 'some/address', config = { ... } }
        }
      }
  end}
```

If you're feeling lucky and want all the bleeding edge features (might require Neovim HEAD):
```lua

  use { 'Vhyrro/neorg', branch = 'unstable', config = function()
      require('neorg').setup {
        load = {
          ["your.module"] = { git_address = 'some/address', config = { ... } }
        }
      }
  end}
```

Then run `:PackerSync`

# WIP
As can be seen, this plugin is a work in progress - these magical features don't come out of nowhere, you know. Despite not providing any end-user features *yet*, it does provide an incredible foundation for developers willing to spend some time writing code for the plugin:
- The module system; the module system is an extensible way to manage and interface with code. Modules are pay-for-what-you-use tables that can get loaded and unloaded at will. They can subscribe to events using the powerful event system and can directly communicate with each other - they can even expose their own public APIs and configuration to be edited by the user. Example modules can be found [here](lua/neorg/modules/core) and a full tutorial for developing with modules can be found [in the CREATING_MODULES document](https://github.com/Vhyrro/neorg/blob/main/docs/CREATING_MODULES.md).
- The event system; the event system is the way for said modules to communicate. Events can be broadcast to all subscribed modules or to individual modules as well, they can hold any sort of data you'd want to transport to another plugin, things like the current cursor position, line content etc. The choice is yours really.

Note that the neorg API may (and probably will be) subject to change! I'll try to refrain from breaking changes unless absolutely necessary, and will let developers know a while beforehand so they can update their modules. The API will stabilize after neorg becomes a bit more mature, so stick with me for now!

# Usage Questions
A lot of people are asking about how to use neorg - so let me reinstantiate what can be seen in the [WIP](#wip) section.

Since neorg is a very young project, there are currently no features *for the end user*. This mean you can't insert your favourite headings and take notes just yet. The focus as of right now is on the **core**, the very foundation neorg is built on. Without a solid core, you can't make a solid plugin, correct? A weak core would also directly impact both the longevity *and* extensiblity, and we want this plugin to live for as long as possible :P

A flowchart is in the works to show exactly where we're headed, so you won't have to be confused anymore. Until then the [github project page](https://github.com/Vhyrro/neorg/projects) should suffice for the very close future.

If there's anything you should know *for now* is that neorg (obviously) only triggers on .norg and .org files. So if you're testing your favourite module or something and nothing happens that might be a potential case.

A GitHub wiki is also in the process of being made! There you will see a lot of the necessary info for how to load community-made modules etc.

TL;DR - all we need is just a little more time, sorry about that :)

# Consult The Wiki!
The entire structure of neorg's core can be a bit complex, so it's definitely worth your time to read the docs! For now you can take a look at them [here](docs/README.md), but in the future the actual github wiki will be available.

# Contributing
I really looove contributions! That's what this whole project is about - it's a really big plugin, so any help is appreciated :heart:. Don't know what to implement? Don't worry, a [roadmap](https://github.com/Vhyrro/neorg/projects) is available (it doesn't describe *all* features to be implemented, but should give you a solid idea!).

Come chat with me on [discord](https://discord.gg/T6EgTAX7ht)!

Also, if you love what I do and want to professionally support my work, boost development etc. drop me a few bucks will ya. Making this my job would be like a dream come true.

Links for the rich lads:
- [Buy me a coffee](https://www.buymeacoffee.com/vhyrro)
- [Donate directly on Paypal](https://paypal.me/ewaczupryna?locale.x=en_GB)
- [Support me on patreon!](https://patreon.com/vhyrro)
