# GitConventions

## .gitignore files
* [.gitignore standalone (v0.1.5)](gitignore/standalone/.gitignore)

## General
Use [Sourcetree](https://www.sourcetreeapp.com/) or the terminal to connect to and work with the repository.
We use a modified version of [git flow](http://nvie.com/posts/a-successful-git-branching-model/) to get a structured branching.
* The master branch is used for the last stable build. This build should not have any features in development in order to be used for presentations or exhibitions.
* The develop branch has always a working copy. You can commit to the develop branch for simple changes, as long as it doesn't break the copy.
* Use feature branches which start from and go back into the develop branch for developing new features.
* Use hotfix branches from the master branch which go back into the master as well as develop if necessary.
* Use Release Branches for minor and major releases, but not for revisions
* Use the sourcetree's git flow solution, if you don't feel 100% confident with the terminal

## Messages
```
<Type> <subject>

<Body>
```
* Messages are written in imperative present tense.
 * **DO**    ADD present tense rule to conventions
 * **DON'T** ADDED present tense rule to conventions
 * **DON'T** ADDS present tense rule to conventions

### Type
Types are always written in capital letters  
The following types are allowed:
 * **Add**
   * Use if you add files to the repository
 * **Change**
   * Use if you change code
 * **Update**
   * Use if you update the unity version, plugins or assets
 * **Tweak**
   * Use if you did changes on gameplay values or asset properties, but didn't change any code
 * **Remove**
   * Use if you delete files
 * **Fix**
   * Use if you fix bugs
 * **Doc**
   * Use if you do documentation work like adding comments
 * **Refactor**
   * Use if you clean up functions or file structures

### Subject
* The subject starts with a lower case letter
* Between the Type and the subject there is one space
* It is a short precise explanation of the committed changes
* it should be no longer than 72 characters

### Body
* The body is an optional detailed description of the changes
* Between the subject line and the body there is one empty line
* For the body every kind of formatting is allowed
