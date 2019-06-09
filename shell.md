# Shell

## Is bash scripting the same as shell scripting?

[scripts - Is bash scripting the same as shell scripting? - Ask Ubuntu](https://askubuntu.com/questions/172481/is-bash-scripting-the-same-as-shell-scripting)

## Shebang

```shell
#!/usr/bin/env bash
```

[What is the preferred Bash shebang? - Stack Overflow](https://stackoverflow.com/questions/10376206/what-is-the-preferred-bash-shebang)

## Perform an action for every sub-directory in a directory

```shell
for D in *; do
    if [ -d "${D}" ]; then
        echo "${D}"   # your processing here
    fi
done
```

[command - Perform an action in every sub-directory using Bash - Stack Overflow](https://stackoverflow.com/questions/4000613/perform-an-action-in-every-sub-directory-using-bash)

## COPY

| Option | Effect                                                |
| :----- | :---------------------------------------------------- |
| -a     | archive files                                         |
| -f     | force copy by removing the destination file if needed |
| -i     | interactive - ask before overwrite                    |
| -l     | link files instead of copy                            |
| -L     | follow symbolic links                                 |
| -n     | no file overwrite                                     |
| -R     | recursive copy (including hidden files)               |
| -u     | update - copy when source is newer than dest          |
| -v     | verbose - print informative messages                  |

[cp command in Linux/Unix | copy files/directories](https://www.rapidtables.com/code/linux/cp.html)
