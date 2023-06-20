# Ranger Keybindings
The following custom keybindings can be added to the `rc.conf` file.

## xclip
Copy the content of a file using `xclip`.

```bash
# copy text file content to clipboard
map y+ shell FILE_CONTENT="`file -b %s|cut -d\, -f1`"; grep -q text <<< $FILE_CONTENT && xclip -r -selection clipboard < %s || echo "Can't copy '$FILE_CONTENT' -> %s"
# copy text file content to selection
map y- shell FILE_CONTENT="`file -b %s|cut -d\, -f1`"; grep -q text <<< $FILE_CONTENT && xclip -r < %s || echo "Can't copy '$FILE_CONTENT' -> %s"
```
