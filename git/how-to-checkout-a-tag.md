# How to checkout a tag

```bash
# check tag list
$ git tag -l

# checkout a specific tag:
$ git checkout tags/<tag_name>

#Even better, checkout and create a branch (other you will be on a branch named after the revision number of tag):
$ git checkout tags/<tag_name> -b <tag_name>
```
