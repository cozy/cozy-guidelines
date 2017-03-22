# Git Workflow

## Table Of Contents

[Git Commit Guidelines](#commit)
  - [Commit Message Format](#format)
  - [Type](#type)
  - [Subject](#subject)
  - [Emoji](#emoji)
  - [Body](#body)


## <a name="commit"></a> Git Commit Guidelines

We have very precise rules over how our git commit messages can be formatted. This leads to **more
readable messages** that are easy to follow when looking through the **project history**.  But also,
we use the git commit messages to **create change log**.


### <a name="format"></a> Commit Message Format

Each commit message consists of a **header** and a **body**. The header has a special
format that includes a **type**, a **subject** and an **emoji**:

```
<type>: <subject> (<emoji>)
<BLANK LINE>
<body>
```

The header is mandatory and the emoji of the header is optional. (Limit to 50 characters or less<sup>[ref](https://chris.beams.io/posts/git-commit/#limit-50)</sup>)

Any line of the commit message cannot be longer 72 characters
<sup>[ref](https://chris.beams.io/posts/git-commit/#wrap-72)</sup>!
This allows the message to be easier to read on GitHub as well as in various git tools.


### <a name="type"></a> Type

Must be one of the following
<sup>[ref](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#type)</sup>:

* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing
  semi-colons, etc)
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **perf**: A code change that improves performance
* **test**: Adding missing or correcting existing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation
  generation


### <a name="subject"></a> Subject

The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* Capitalize first letter<sup>[ref](https://chris.beams.io/posts/git-commit/#capitalize)</sup>
* no dot (.) at the end


### <a name="emoji"></a> Emoji :+1:

Commit messages are usually boring. But with emojis you can make them slightly less boring.

[An emoji guide for your commit messages](https://gitmoji.carloscuesta.me/) :heart_eyes:


### <a name="body"></a> Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes".
The body should include the motivation for the change and contrast this with previous behavior.
