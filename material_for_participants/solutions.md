# Solutions for Optional Exercises

## 1: Renaming Files
1. No. While this would create a file with the correct name, the incorrectly named file still exists in the directory and would need to be deleted.
2. Yes, this would work to rename the file.
3. No, the period(`.`) indicates where to move the file, but does not provide a new file name; identical file names cannot be created.
4. No, the period(`.`) indicates where to copy the file, but does not provide a new file name; identical file names cannot be created.

## 2: Copy with Multiple Filenames

When `cp` is given two arguments and the second is a destination directory `cp` copies the files to the destination directory.

If given three or more arguments, `cp` throws an error such as the one below, because it is expecting a destination directory name as the last argument.

```console
cp: target 'basilisk.dat' is not a directory
```

## 3: More on Wildcards
```console
$ cp *calibration.txt backup/calibration
$ cp 2015-11-* send_to_bob/all_november_files/
$ cp *-23-dataset* send_to_bob/all_datasets_created_on_a_23rd/
```