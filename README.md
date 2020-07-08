# Useful Bash Commands that I always forget 🤦‍️

### Xargs

```cat dois-to-check.txt | xargs -P 8 -L1 ./check-file-exists.sh &> output.log &```

`-P` is parallel tasks

`-L` is input one line as one argument

```cat dois-to-check.txt | head | xargs -I '{}' -L1 echo basu '{}'.txt```
`{}` is used to capture arguments, remember to use `-I '{}''` for this to work

### Running things in background and redirect to a file

```./check-file-exists.sh &> output.log &```

`&>` output to file and `&` run in background

### Screen

- List all screen sessions `screen -ls`
- Detach screen session and run in background `Ctrl + a d`
- Re-attach to screen session, first list screen sessions using 
```
screen -ls
There is a screen on:
	7316.pts-0.long-running-tasks	(06/24/20 09:47:02)	(Detached)
1 Socket in /run/screen/S-ubuntu.

screen -r pts-0.long-running-tasks

```

### Read line by line

`while read -r line; do COMMAND; done < input.file`

### Docker Compose start bash

`docker-compose run app bash`

### JQ

```curl "https://bhlah" | jq '.articles[].pageStart'```
