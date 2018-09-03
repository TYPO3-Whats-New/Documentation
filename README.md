# TYPO3 What's New Slides

## Document Scope

Simple documentation how to work with and contribute to the TYPO3 What's New Slides.

## Introduction

### Technology Behind the What's New Slides

The TYPO3 What's New Slides use [LaTeX](https://www.latex-project.org/), a well-known typesetting system, as the source code for the slides. To be more precise, we are using the LaTeX document class ["Beamer"](https://bitbucket.org/rivanvx/beamer/wiki/Home). The sources are then rendered ("converted") into PDF documents, reviewed and published.

### Git Repositories

The LaTeX sources are stored and managed at [GitHub](https://github.com/TYPO3-Whats-New/). Every What's New Slides version has its own Git repository, for example `TYPO3-v9.4-dev`, `TYPO3-v9.5-dev`, etc.

### Git Branches (Translations)

The **English** version of the What's Slides is always the primary language. From this language, a number of translations are created into other languages by the TYPO3 What's Team. Each language uses its own [Git branch](https://www.atlassian.com/git/tutorials/using-branches). This means, a repository such as `TYPO3-v9.4-dev` has multiple branches, with `English` as the *default branch*. Once the English version of the What's New Slides has been completed, several branches are created from the default branch, e.g. `Dutch`, `German`, `French`, etc. From this point on, translators are only working on *their* language branch.

### Rendering by Webhook

By transferring the updated LaTeX sources back to GitHub (`git push`), a webhook is executed, which triggers the rendering process. The LaTeX code is converted into a PDF document by using the latest commit in the appropriate Git repository and Git language branch, e.g. `TYPO3-v9.4-dev`/`Dutch`.

If the rendering process was successful (no syntax errors in the LaTeX source), the PDF document can be downloaded and reviewed.

## Preparation

*(TODO: to be documented)*

## Environment Setup

Two options exist in general, how to work with the LaTeX sources and Git repositories. Both have pros and cons.

* Working directly in GitHub (no Git client required)
* Working on your local copy of the repository

### Working directly with GitHub

GitHub offers an _Edit_ function, which allows users to work with the files directly in their browsers. The main benefit with this approach is that users do not need to install any Git client software on their local machine. In fact, users do not need to know any Git commands necessarily.

Therefore, there is nothing to set up or configure, expect the settings at GitHub (see section "[Preparation](#Preparation)" above).

### Working on a Local Git Repository

The second option is to transfer the LaTeX sources from GitHub to your local machine. The `git clone` command creates a copy of the remote repository and let's users work on their local copy. To render the updated/translated slides to a PDF document, the local changes can be pushed back to GitHub (`git push`), which triggers the webhook [as described above](#Rendering by Webhook) and generates the PDF file.

This approach requires some basic knowledge in Git (e.g. how to "clone" a repository, how to _commit_ changes, how to _push_ local commits to the remote server, etc.), but also offers some great benefits. You do not need to be online when working with the What's New Slides and you can choose the software to edit the LaTeX files.

To set up your local environment, the following actions are required.

* Install a Git client (command line tool, or one of [Git GUI clients](https://git-scm.com/downloads/guis).
* Configure your local Git client to use your **name** (first and last name) and **email address** as the author of code commits.
* Make sure, you can access the What's New Slides' [Git repository](https://github.com/TYPO3-Whats-New) (read and write).

## Editing the Slides (e.g. Translations)

The points listed above already provide most of the information require to work with the What's New Slides. When you work on a translation (e.g. from English to Dutch), the most important point is to work on the correct **Git branch** (e.g. `Dutch`).

If you work directly with GitHub, a dropdown box allows you to switch to a specific branch:

*(TODO: screenshot to be added)*

If you work on your local repository, make sure you checkout the correct branch (e.g. `Dutch`):

```
$ git checkout Dutch
```

You can check the available branches after you cloned from the remote repository (list under "Remote branch"):

```
$ git remote show origin
```

### Known LaTeX Pitfalls

Some characters have a special meaning in LaTeX. Therefore, they need to be *escaped* (prepended by a slash), if they are not inside a code listing (`lstlisting`). For example:

*(TODO: examples to be added)*

### Render LaTeX to PDF

As described [above](#Rendering by Webhook), only a `git push` is required to trigger the LaTeX to PDF rendering chain. You can download the PDF document, review it, and repeat the process as often as you want.

Please contact the project leader to learn the exact URL to download the PDF document.
