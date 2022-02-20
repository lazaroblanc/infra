# Commonly used commands

## Transfer files/directories to another server
```
rsync -rpahv -e "ssh -i ~/.ssh/lazaro" --progress <SRC_PATH> <DEST>:<DEST_PATH>`
```