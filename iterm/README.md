Open `~/.bash_profile` in vim:
```
$ vi ~/.bash_profile
```
and add to the file
```
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u \[\033[32m\]\W/ >\$(parse_git_branch)\[\033[00m\] $ "
```

Save and quit, reload:
```
$ source ~/.bash_profile
```
