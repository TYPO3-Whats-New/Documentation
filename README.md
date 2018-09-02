# TYPO3 What's New Slides

## Document Scope

Simple documentation how to work with and contribute to the TYPO3 What's New
Slides.

## Introduction

### Technology Behind the What's New Slides

The TYPO3 What's New Slides use [LaTeX](https://www.latex-project.org/), a well-known typesetting system, as the source code for the slides. To be more precise, we are using the LaTeX document class ["Beamer"](https://bitbucket.org/rivanvx/beamer/wiki/Home). The sources are then rendered ("converted") into PDF documents, reviewed and published.

### Git Repositories

The LaTeX sources are stored and managed at [GitHub](https://github.com/TYPO3-Whats-New/). Every What's New Slides version has its own Git repository, for example `TYPO3-v9.4-dev`, `TYPO3-v9.5-dev`, etc.

### Git Branches (Translations)

The **English** version of the What's Slides is always the primary language. From this language, a number of translations are created into other languages by the TYPO3 What's Team. Each language uses its own [Git branch](https://www.atlassian.com/git/tutorials/using-branches). This means, a repository such as `TYPO3-v9.4-dev` has multiple branches, with `English` as the *default branch*. Once the English version of the What's New Slides has been completed, several branches are created from the default branch, e.g. `Dutch`, `German`, `French`, etc. From this point on, translators are only working on *their* language branch.

### Rendering by Webhooks

By transferring the updated LaTeX sources back to GitHub (also known as `git push`), a webhook is executed, which triggers the rendering process. The LaTeX code is converted into a PDF document by using the latest commit in the appropriate Git repository and Git language branch, e.g. `TYPO3-v9.4-dev`/`Dutch`.

If the rendering process was successful (no syntax errors in the LaTeX source), the PDF document can be downloaded and reviewed.

## Preparation

*(to be documented)*

## Environment Setup

In general, two options exist, how to work with the LaTeX sources and Git repositories. Both have pros and cons.

* Working directly in GitHub (no Git client required)
* Working on your local copy of the repository

### Working directly in GitHub

*(to be documented)*

### Working on a Local Git Repository

*(to be documented)*
