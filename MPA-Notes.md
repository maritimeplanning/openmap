## Current Branch
The `v5112` branch is the one used for all MPA edits/changes.  This is the branch that is recompiled and released to the artifactory server.

**DO NOT MERGE OR MAKE CHANGES ON MASTER**

## Updating
Essentially, you want to `fetch` the latest from his repo (`bbn`), make a new branch from the 'Current Branch' above with the latest tag name (no '.' s), the rebase his latest tag.

From the 'current branch' - in this case `v5112`

```bash
# Checkout the "master branch"
git co master

# Get the latest from BBN's repository
git fetch bbn

# Rebase the master branch with what came from bbn
git rebase bbn/master

# Check the tags
git tags

# Checkout a branch from the latest tag (which at this time is v5.1.12)
git co v5.1.12
git co -b v5112

# Cherry-pick changes from the previous "MPA" branch onto this one
stree # Done in Source Tree

# Generate the new set of jars - the '5.1.1' indicates the new version #
make_jars 5.1.12

```

Then upload the jar files (in 'dist/') to Artifactory.

## Compilation
To achieve cleaner integration with the MPA codebase, the library is recompiled with Java 7.

## Changes
For details about the changes made to the library, see the commit history of the currently active MPA version branch
