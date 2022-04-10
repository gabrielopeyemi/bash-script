# Some cool bash commands


## React-native add path
```
function path(){
    export ANDROID_HOME=$HOME/Android/Sdk
    export PATH=$PATH:$ANDROID_HOME/emulator
    export PATH=$PATH:$ANDROID_HOME/tools
    export PATH=$PATH:$ANDROID_HOME/tools/bin
    export PATH=$PATH:$ANDROID_HOME/platform-tools
}
```


## Start and run React-native
```
function rn(){
    path
    npx react-native run-android
    npx react-native start
}
```

## Commit to git
```
function commit (){
    local myCommit="$1"
    local message="You have commited a new change: "

    git stage . && git add . && git commit -m "$1"

    echo "You have commited a new change: $1"
    alert "You have commited a new change: $1"
}
```

## Push to git 
```
function push(){
    branchname=$(git describe --contains --all HEAD)
    git push --set-upstream origin $branchname
    echo "you just pushed to: $branchname"
    alert "you just pushed to: $branchname"
}
```

## Create new branch
```
function newbranch(){
    git checkout -b "$1"
}
```

## Clear terminal easily
```
alias c='clear'
```

## Open Bash script easily
```
alias bash='code ~/.bashrc'
```

## Switch on keyboard Light
```
function backLight(){
    xset led on
}
```