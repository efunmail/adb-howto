## PULL certain files from Android device

- LIST the files

```sh
adb shell "cd /sdcard/Download/$SOME_DIR"; ls -l | tr -s ' ' | cut -d ' ' -f 8" \
> filenames.txt
```

- PULL the files

```sh
cat filenames.txt | xargs -I {}  bash -c "adb pull -a /sdcard/Download/$SOME_DIR/{}"
```
