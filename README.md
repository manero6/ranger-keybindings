# Ranger Keybindings
The following custom keybindings can be added to the `rc.conf` file.

## 7z
Extract zip files using `7z`.

```bash
# extract the zip file in a new directory, whose name is the same as the zip file, but without extension
map x7 shell FILE_TYPE="`file -b %s|cut -d\, -f1`"; ZIP_FILE_NOEXT="`echo %s|rev|cut -f2- -d\.|rev`"; grep -iq zip <<< $FILE_TYPE && 7z x %s -o"$ZIP_FILE_NOEXT" || echo "Can't extract '$FILE_TYPE' -> %s"
# extract the zip file without creating a new directory
map xx7 shell FILE_TYPE="`file -b %s|cut -d\, -f1`"; grep -iq zip <<< $FILE_TYPE && 7z x %s || echo "Can't extract '$FILE_TYPE' -> %s"
```

---

## xclip
Copy the content of a file using `xclip`.

```bash
# copy text file content to clipboard
map y+ shell FILE_TYPE="`file -b %f|cut -d\, -f1`"; grep -iq text <<< $FILE_TYPE && xclip -r -selection clipboard < %f || echo "Can't copy '$FILE_TYPE' -> %f"
# copy text file content to selection
map y- shell FILE_TYPE="`file -b %f|cut -d\, -f1`"; grep -iq text <<< $FILE_TYPE && xclip -r < %f || echo "Can't copy '$FILE_TYPE' -> %f"
```

