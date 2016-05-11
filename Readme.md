### Applescript project running scripts

A collection of automation scripts for iterm for running various projects

#### Howto

1. Clone repo somewhere
2. `cd` into dir and make files executable `chmod +x [files]`

BONUS: Put this in your `~/.zshrc` if you are running zshell for additional awesomeness

```
export ITERMSCRIPTSPATH=the/dir/where/you/cloned/the/repo
function runproject {
  osascript $ITERMSCRIPTSPATH/$1 2>/dev/null || echo "No such script to run: $1"
}
function _completerunprojectscripts {
  reply=($(ls $ITERMSCRIPTSPATH))
}

compctl -K _completerunprojectscripts runproject
```
