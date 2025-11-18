# curlagent

A wrapper around curl to automatically add the --user-agent with a random[^1] useragent


useful for quick security testing when you don't want your user agent to be
curl.


[^1]: random but cached until --agent-refresh

## setup

create a text file in $HOME/.config/curlagent/agents each line containing
a user agent string

Perhaps [pzb](https://github.com/pzb)'s [list](https://gist.github.com/pzb/b4b6f57144aea7827ae4)

```
curl \
  --create-dirs \
  --output ~/.config/curlagent/agents \
  https://gist.githubusercontent.com/pzb/b4b6f57144aea7827ae4/raw/user-agents.txt
```

## usage

`curlagent [--agent-refresh] [CURL_ARGS]`

by default curlagent picks a random user agent from the agents file and caches
it for future runs.

--agent-refresh  makes curlagent pick a new user agent

