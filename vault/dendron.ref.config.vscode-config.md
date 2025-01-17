---
id: 19a0ea9d-7292-4a68-bc6f-ffd462a54bc5
title: VS Code Config
desc: ''
updated: 1642067977633
created: 1619541378119
---

## Access

You can access these configurations through the [VS Code Settings](https://code.visualstudio.com/docs/getstarted/settings) if you search for "Dendron".

![[dendron.ref.config#legend:#*]]

## folders

- type: folders[]

This entry is a list of folders that are tracked by your workspace.
The entries here should mirror the vaults from [[dendron.topic.vaults]]

Each folder entry has the following structure

```json
{
    "folders": [
        {
            // relative path to vault from workspace
            "path": "vault",
            // name for folder (default to folder anme)
            "name": "optional"
        }
    ]
}
```

## dendron.defaultTimestampDecorationFormat 
- default: DATETIME_MED
- type: string
- values (see description of values in [luxon style formatting][luxon-style-formatting]) 
    * DATETIME_FULL
    * DATETIME_FULL_WITH_SECONDS
    * DATETIME_HUGE
    * DATETIME_HUGE_WITH_SECONDS
    * DATETIME_MED
    * DATETIME_MED_WITH_SECONDS
    * DATETIME_SHORT
    * DATETIME_SHORT_WITH_SECONDS
    * DATE_FULL
    * DATE_HUGE
    * DATE_MED
    * DATE_MED_WITH_WEEKDAY
    * DATE_SHORT
    * TIME_24_SIMPLE
    * TIME_24_WITH_LONG_OFFSET
    * TIME_24_WITH_SECONDS
    * TIME_24_WITH_SHORT_OFFSET
    * TIME_SIMPLE
    * TIME_WITH_LONG_OFFSET
    * TIME_WITH_SECONDS
    * TIME_WITH_SHORT_OFFSET

Decide how human readable timestamp decoration is displayed

## dendron.copyNoteUrlRoot
- type: string
- default: none

override root url when getting note url

## dendron.linkSelectAutoTitleBehavior
- type: string
- default: slug
- options:  ['none', 'slug']

Control title behavior when using selection2link with lookup

## dendron.defaultLookupCreateBehavior
- type: string
- default: selectionExtract
- options:  ['selection2link', 'selectionExtract']

when creating a new note with selected text, define behavior for selected text

## dendron.rootDir
- type: string
- default: 

location of Dendron workspace

## dendron.logLevel
- type: string
- default: info
- options:  ['debug', 'info', 'error']

control verbosity of Dendron logs

## dendron.trace.server
- type: string
- default: messages
- options:  ['off', 'messages', 'verbose']

LSP log level

## dendron.serverPort
- type: number
- default: none

port for server. If not set, will be randomly generated at startup.

[luxon-style-formatting]: https://moment.github.io/luxon/#/formatting

## dendron.watchForNativeWorkspace
- type: boolean
- default: false

When true, Dendron will watch workspaces to detect when a native workspace is
created to simplify initialization. This is no longer required, Dendron instead
initializes itself when a native workspace is created. Enabling this may cause
performance issues and crashes in workspaces that contain lots of files, it's
recommended that you keep this `false`.
