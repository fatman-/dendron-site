---
id: lamzybrD6SgQlJ9BpwkQk
title: Native Workspaces
desc: ''
updated: 1636540012593
created: 1634020995541
---

## Setup

As a reminder, these instructions are temporary until we add support for
initializing native workspaces. We're sorry if they look confusing, we'll be
improving native workspaces soon to make this simpler.

These instructions assume that you have an existing project, and you are trying
to set up a Native workspace to take notes with Dendron.

- Create a folder in your project for the notes. For example, a folder named `notes`.
- Use the command "Dendron: Initialize Workspace", and type the path to the notes folder.
- Initialize a blank workspace at this folder.
- Use the "Open Recent" command to go back to your project.
- Move the `dendron.yml` file from the notes folder to the root of the project.
- Open `dendron.yml`, and edit the `vaults` section so it looks like the following:
  ```yml
  vaults:
      -
          fsPath: notes/vault
  ```
  Save the file.
- Use the command "Reload Window". Dendron should now start up, and you should be able to use all Dendron features.

## Automatic Initialization

Dendron looks at files that are added to non-Dendron workspaces to automatically
start everything if a native Dendron workspace is created. This typically should
not affect your experience with VSCode, but you can disable it if you experience
any issues using the [[dendron.watchForNativeWorkspace|dendron://dendron.dendron-site/dendron.ref.config.vscode-config#dendronwatchfornativeworkspace]]
option in the extension settings.