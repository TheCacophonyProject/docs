---
title: 'Working with Typescript'
---

### Visual Studio Code
In order to ignore the non source files in visual studio, Edit the settings.json files to include:
    "files.exclude": {
        "**/*.js.map": true,
        "**/*.js": {"when": "$(basename).ts"}
    },
    
Do this by going to **File/Preferences** and searching for "_exclude_".   Then look for a link to edit settings.json. 