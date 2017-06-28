# Questions

## Status

[![Build Status](https://travis-ci.org/dhbw-stginf16a/questions.svg?branch=master)](https://travis-ci.org/dhbw-stginf16a/questions)

## Project Structure

```
.
├── FileStructure.md
├── questions
│   ├── Branding & Product
│   │   └── ...
│   ├── Economics
│   │   └── ...
│   ├── PM General & Planing
│   │   └── ...
│   ├── Price & Promo
│   │   └── ...
│   ├── RASIC & Project Manager
│   |   └── ...
│   └── project.qepr
└── README.md
```

Every question is stored as a single file in a category-folder.

## How to create questions

Questions should only be edited using the [Editor](https://github.com/dhbw-stginf16a/questions-tools/releases). The Editor supports all types of supported questions and offers a three-state-approval system. Every question, which is work in progress should be in the draft state. Once a question is finished it can be set into review-state so someone else could review and approve them.
Only approved Questions can be released.

## Builds and Releases

Every time new commit are pushed into the GitHub repository Travis will be triggered to automatically test and build the project using a self-written [Parser](https://github.com/dhbw-stginf16a/questions-tools/blob/master/parseQuestion.py).
This ensures the integrity of the questions and generates one large file, as specified in the [file structure](FileStructure.md), to share it with the other teams.

A question with errors in draft-state will only trigger warnings. Everything broken in review or approved state will make the script fail (The current build status is visible in the small icon on top of this page).

If a commit is tagged the single file with all questions is will also be [released](https://github.com/dhbw-stginf16a/questions/releases).
