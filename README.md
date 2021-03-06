## TwitchView
# Requirements
To install the dependencies, simply run the following:
>brew install jq mpv

# How to use
Simply run the who.sh script and it will walk you through obtaining the information needed to run properly.

# Run From rc File
To run this from an rc file, download who.sh from the rc folder in to your ~/.config folder and append the following to the end of your rc file

```
watch() {
    if [ "$1" = "who" ] 
    then 
        ./.config/who.sh 
    else 
        if [ ! command -v mpv &> /dev/null  ]
        then
            echo "Missing dependency: mpv"
            exit
        fi
        mpv -start 15 --force-seekable=yes https://twitch.tv/"$1"
    fi 
}
```
Make sure to source your rc file after adding the code above.

# Usage
From rc file
```
watch who - Shows online streamers you follow
watch <name> - Opens an mpv stream for the streamer
```
From script
```
./who watch who - Shows online streamers you follow
watch <name> - Opens an mpv stream for the streamer
```
