# Ranger Keybindings
The following custom keybindings can be added to the `rc.conf` file.

## xclip
Copy the content of a file using `xclip`.

```bash
map y+ shell xclip -selection clipboard < %s
map y- shell xclip < %s
```
