
* Take a look at `.git/config` to see what this linkage looks like.  

```
$ cat .git/config

[core]
	repositoryformatversion = 0
	filemode = true
	bare = false
	logallrefupdates = true
	ignorecase = true
	precomposeunicode = true
[remote "origin"]
	url = https://github.com/hpreston/imapex-git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
[branch "shakespeare"]
	remote = origin
	merge = refs/heads/shakespeare
```

