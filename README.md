# Ranger Keybindings
The following custom keybindings can be added to the `rc.conf` file.

## xclip
Copy the content of a file using `xclip`.

```bash
map y+ shell FILE_CONTENT="`file -b %s|cut -d\, -f1`"; [[ $FILE_CONTENT =~ "text" ]] && xclip -selection clipboard < %s || echo "can't copy '$FILE_CONTENT'"
map y- shell FILE_CONTENT="`file -b %s|cut -d\, -f1`"; [[ $FILE_CONTENT =~ "text" ]] && xclip < %s || echo "can't copy '$FILE_CONTENT'"
```
