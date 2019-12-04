# GitConventions

## Downloads
* [.gitignore for Unity (v0.2.0)](gitignore/.gitignore)
* [.gitattributes for Unity (v0.2.0)](gitignore/.gitattributes)
* [Speical Folder Structure](SpecialFolders.zip)

## General
We use a simplified version of [git flow](http://nvie.com/posts/a-successful-git-branching-model/). There is a master branch that is holy as it should be, there is a develop branch that always works, but might get messy and there are feature and release branches to get structure in there.
* Recommended Software: [Sourcetree](https://www.sourcetreeapp.com/) (Alternatives: [Terminal](https://git-scm.com/docs), [Git Kraken](https://www.gitkraken.com/), [Git Tower](https://www.git-tower.com/))
* The master branch is used for the last stable build. This build should not have any features in development in order to be used for presentations or exhibitions.
* The develop branch has always a working copy. You can commit to the develop branch for simple changes, as long as it doesn't break the copy.
* Use feature branches which start from and go back into the develop branch for developing new features.
* Use Release Branches for minor and major releases
* Spilt up commits with multiple changes that are not connected

## Special folders
* Use `ROOT/Builds` for builds.  
Recommended structure: `ROOT/Builds/Platform/Version/ProductName` (e.g.`ROOT/Builds/Android/0.8.3.17/Marbloid.apk`)
* Use `ROOT/Data` for data like screenshots and videos.  
Recommended structure: `ROOT/Data/Screenshots`, `ROOT/Data/Videos`
* Use `ROOT/Assets/Temp` for files that you need in the project, but which should not be included in the repository.
* Use `ROOT/FMOD` for the fmod project if applicable.

## Commit messages
```
<Type> <subject>

<Body>
```
Messages are written in imperative present tense.
* **DO**    `Add present tense rule to conventions`
* **DON'T**    `Added present tense rule to conventions`
* **DON'T** `Added present tense rule to conventions`
* **DON'T** `Adds present tense rule to conventions`

### Type
Types are always written in capital letters  
The following types are allowed:
 * **Add**
   * Use if you add files to the repository
 * **Change**
   * Use if you change code
 * **Fix**
   * Use if you fix bugs
 * **Remove**
   * Use if you delete files
 * **Update**
   * Use if you update the unity version, plugins or assets
 * **Automatic**
   * Use when you run automatic scripts like automatic code reformating

### Subject
* The subject starts with a lower case letter
* Between the Type and the subject there is one space
* It is a short precise explanation of the committed changes

### Body
* The body is an optional detailed description of the changes
* Between the subject line and the body there is one empty line
* For the body every kind of formatting is allowed
