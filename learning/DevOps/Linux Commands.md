# Linux command format

```shell
command options arguments
```

The `commands` determine what operations needs to be performed. some common commands include:
- `cd` -> change directory.
- `ls` -> list items in a directory.
- `pwd` -> get present working directory.
- `mkdir` -> make directory.
- `rmdir` -> remove directory.
- `rm` -> remove (used to remove files).
- `touch` -> create new file.
- `mv` -> move files.
- `cp` -> copy files/directories.

The `options` determine how the command may be performed. You can get the list of all the options associated with a command by running :
```shell
command_name --help
```

Example:
```shell
rm -rf dir1
```
The above command deletes all the files present in the `dir1` directory and deletes the directory itself.

```shell
cp /home/vagrant/dir1/  /home/vagrant/dir2/
```

the above file copies `dir1` and paste it in `dir2`

```shell
 touch file{1..5}.txt
```
the above command creates 5 files => `file1.txt`, `file2.txt`, `file3.txt`, `file4.txt`, `file5.txt`.
