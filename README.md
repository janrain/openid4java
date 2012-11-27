janrain openid4java mirror
================================================================================

Initial Setup
--------------------------------------------------------------------------------

- `git clone ssh://git@github.com/janrain/openid4java`
- `cd openid4java`
- `git config -e`

```
[core]
    repositoryformatversion = 0
    filemode = true
    bare = false
    logallrefupdates = true
    ignorecase = true
    precomposeunicode = false
[svn-remote "svn"]
    url = http://openid4java.googlecode.com/svn/trunk
    fetch = :refs/remotes/git-svn
[remote "origin"]
    url = ssh://git@github.com/janrain/openid4java
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
    remote = origin
    merge = refs/heads/master
[branch "upstream"]
    remote = origin
    merge = refs/heads/upstream
```

Sync Mirror
--------------------------------------------------------------------------------

- `git checkout upstream`
- `git svn rebase`
- `git push origin HEAD`
- `git checkout master`
- `git merge --rebase upstream`

Sync Mirror
--------------------------------------------------------------------------------

Never make any changes in the `upstream` branch. That branch should always be a
direct mirror of the upstream svn repo.
