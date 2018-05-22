# Git Flow +

## Branching
### The base: ‘develop’ and ‘master’ branches
* Active development takes place on the ‘develop’ branch
* Stable versions are merged with the ‘master’ branch, preferably periodically, like after every sprint or after finishing a project

### For each *project* a new branch *(optional)*
* Branch off from **‘develop’**
* Name: **project/***<descriptive_name>*
* **PR** to **‘develop’**
* For functionality bigger than a single feature branch (bigger than a single sprint)
* For projects like internships
* Comparable with the **‘develop’** branch in smaller project, added to get a quick overview of which functionality was added during specific projects
### For each *feature* a new branch
* Branch off from **‘project/<current_project>’** *if the feature is part of a **project*** or **‘develop’** *if the feature isn’t part of a bigger project*
* Name: **feature/***<descriptive_name>*
* **PR *back*** to **‘project/<current_project>’** or **‘develop’**
### For each *hotfix* a new branch
* Branch off from **‘master’**
* Name: **hotfix/***<descriptive_name>*
* **PR** to **‘develop’** *and* **‘master’**
### For each *release* (i.e. sprint demo) a new branch
* Branch off from **‘develop’**
* Name: **release/***\<version_number>-\<version_name>-\<date yyyy-MM-dd>* *See [Semantic versioning](#Semantic versioning) for \<version_number>*
* Allows us to do some **minor** last minute improvements and bugfixes before merging to **‘master’**
* Add release meta-data (version number (see [Semantic versioning](#Semantic versioning)), build date, etc.)
* Allows us to continue merging new features for future releases to the **‘develop’** branch
* **PR** to **‘develop’** *and* **‘master’**

## Way of working conventions
* **Pull requests (PR’s)** are **reviewed** by **another developer**, preferably a senior developer
* Always merge with **--no-ff** (no fast forward/create new commit even if fast forwarding is possible)
* **Tag** releases on the **‘master’** branch with the version number (see [Semantic versioning](#Semantic versioning)) and date (yyyy-MM-dd)

### Semantic versioning
*\<major>.\<minor>.\<patch>*

**Major version numbers**
Major version numbers must be incremented if there are breaking changes

*Note: Minor- and patch version numbers are resetted back to 0 with a new major release*

**Minor version numbers**
Minor version numbers must be incremented if:
* New features were added
* The current version is *fully* compatible with the previous version within this major version

*Note: Patch version numbers are resetted back to 0 with a new minor release*

**Patch version numbers**
Patch version numbers must be incremented if a bug was fixed on the master branch (using the intended **hotfix** branch)
