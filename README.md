# torchlightsoftware.com
Torchlight website.

## Installation

[Install hugo (~v0.58.3)]()

## Run Dev Server

```bash
hugo server
```

## Deploy to Production

```bash
# run hugo to put files in the public directory
hugo
```

Then notify Brandon.  He will:

```bash
git pull
static public # to take a quick peek and make sure everything looks good
git push deploy master
```

This pushes to a git repo at `torchlightsoftware.com:git/torchlightsoftware.com`.  There is a `post-receive` hook on the remote repository with these contents:

```bash
#!/bin/sh
GIT_WORK_TREE=~/torchlightsoftware.com git checkout -f
```

That is sufficient to deploy the static files to `~/torchlightsoftware.com/public`, which is where the dreamhost servers are serving the website from.
