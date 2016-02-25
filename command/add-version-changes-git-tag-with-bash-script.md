# How to genarate VERSION, CHANGES and TAGS with a bash script

* Common task in a software projects release
* * Bump number
* * Update a CHANGES file
* * Commit a new tag to git

```bash
#!/bin/bash

git checkout master
git pull

if [ -f VERSION ]; then
    BASE_STRING=`cat VERSION`
    BASE_LIST=(`echo $BASE_STRING | tr '.' ' '`)
    V_MAJOR=${BASE_LIST[0]}
    V_MINOR=${BASE_LIST[1]}
    V_PATCH=${BASE_LIST[2]}
    echo "Current version : $BASE_STRING"
    V_MINOR=$((V_MINOR + 1))
    V_PATCH=0
    SUGGESTED_VERSION="$V_MAJOR.$V_MINOR.$V_PATCH"
    echo "Will set new version to be $INPUT_STRING"
    echo $SUGGESTED_VERSION > VERSION
    echo "Version $SUGGESTED_VERSION:" > tmpfile
    git log --pretty=format:" - %s" "v$BASE_STRING"...HEAD >> tmpfile
    echo "" >> tmpfile
    echo "" >> tmpfile
    cat CHANGES >> tmpfile
    mv tmpfile CHANGES
    git add CHANGES VERSION
    git commit -m "Version bump to $SUGGESTED_VERSION"
    git tag -a -m "Tagging version $SUGGESTED_VERSION" "v$SUGGESTED_VERSION"
    git push origin --tags
else
    echo "Could not find a VERSION file"
    echo "Init version"
    echo "0.1.0" > VERSION
    echo "Version 0.1.0" > CHANGES
    git log --pretty=format:" - %s" >> CHANGES
    echo "" >> CHANGES
    echo "" >> CHANGES
    git add VERSION CHANGES
    git commit -m "Added VERSION and CHANGES files, Version bump to v0.1.0"
    git tag -a -m "Tagging version 0.1.0" "v0.1.0"
    git push origin --tags
fi
```

I borrowed from [pete-otaqui/Bump a software project's VERSION, add the CHANGES, and tag with GIT](https://gist.github.com/pete-otaqui/4188238)

