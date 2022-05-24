# WeeChat configuration for Twitch.tv
WeeChat terminal IRC client
- https://weechat.org

## Generate a token

1. acccess to "OAuth Password Generator"; semi-official service
 - https://twitchapps.com/tmi/
  - http://help.twitch.tv/customer/portal/articles/1302780-twitch-irc
2. push "Connect to Twitch"
3. copy "oauth:" key

  ```
  oauth:***
  ```

 > https://twitchapps.com/tmi/#access_token=***&scope=chat_login

### Reset/Revoke OAuth key

You must be keep "Twitch Chat OAuth Token Generator" connection

- http://www.twitch.tv/settings/connections

If you push "Disconnect", so IRC connection unavailable;
You have to need re-generate new OAuth key for join IRC

## Add Twitch as a new IRC server
replace TWITCH_NAME to your lowercase Twitch username

```
/server add twitch irc.twitch.tv/6697 -password=oauth:*** -nicks=TWITCH_NAME -username=TWITCH_NAME -ssl
```

> https://www.reddit.com/r/Twitch/comments/2uqews/anybody_here_using_weechat/

## Connect and Join

```
/connect twitch
```

```
/join #CHANNEL_NAME
```

## Set Membership
use for normal IRC client; get user list et al.

```
/set irc.server.twitch.command "/quote CAP REQ :twitch.tv/membership"
```

## Save settings
write settings to files

```
/save
```

## Exit/Close
exit channel

```
/part #CHANNEL_NAME
```

close WeeChat

```
/quit
```

## Buffer
below commands/key very convenience when join 2 or more channels

```
/buffer list
```

### Move buffer-ring
<kbd>Ctrl</kbd> + <kbd>n</kbd> , <kbd>Ctrl</kbd> + <kbd>p</kbd>

### Close buffer
push <kbd>Tab</kbd> completion <code>BUFFER_NAME</code>

```
/buffer close BUFFER_NAME
```

## Window split

### **v**ertical and **h**orizontal split

```
/window splitv
/window splith
```

### Move window
<kbd>F7</kbd> , <kbd>F8</kbd>

### Undo split

```
/window merge
```


https://gist.github.com/ellisonleao/5d871f4bed7f404912c33b41784c1080