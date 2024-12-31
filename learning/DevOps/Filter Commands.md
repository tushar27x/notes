# Filter commands

### Grep

- it is used to find texts from any text input
![[Pasted image 20240723120223.png]]
- it returns the line which contains the word.
- To ignore the case sensitivity we use `-i`
![[Pasted image 20240723120354.png]]

- To find a text in multiple files (including files in an directory).
  The `R` flag is used to search for a word in files stored in subdirectories.
![[Pasted image 20240723120619.png]]

- `grep` has an option `-v` which selects all the lines which **do not** contain the give word
```shell
grep -v firewall anaconda-ks.cfg
```

The above command will return all the lines from the file `anaconda-ks.cfg` which do not contain the word `firewall`

### Less

- it is a reader
- It is similar to `cat` 
```linux
less /etc/passwd
```

### More

- It is exactly same as less


### Head

- Is used to get the first 10 lines of a file
- If you wish to view more or less than 10 lines use a flag `-` followed by the number of lines from the start.
```shell
head -20 anaconda-ks.cfg
```


### Tail

- It is the opposite of head.
- Instead of returning the lines from the start it returns the lines from the end of the file.
```shell
tail anaconda-ks.cfg
```

- the `tail` command has a very useful option which is `-f` which is used to display any changes that are currently being made in the file.
- `-f` flags is particularly useful when we want to see log files and the changes that are being made in these files for troubleshooting purposes.

```shell
tail -f /var/log/messages
```

the above command will open the `/var/log/messages` file and will display all the logs that are being added in it.


### Cut

-  It is used for search operations by filtering the text file based on delimiters
```shell
cut -d: -f1 /etc/passwd
```
The above command is used to get the first column info from the file `/etc/passwd` which contains the information about all the users.

For using `cut` it is very important to know the delimiters.

### AWK

- `awk` is also a searching command which is used to perform advanced search operations using regular expressions

```shell
awk -F':' '{print $1}' /etc/passwd
```
- `-F` is used to specify the delimiter
- `{print $1}` will print the first column.
 
### Sed

- It is a command which used for search and replace.
```shell
 sed -i 's/windows/linux/g' sample.txt
```

the above command will search for all the occurrences of the word 'windows' and replace it with 'linux' in the file `sample.txt`

The same operation can be performed inside vim in command mode by using the command
```shell
:%s/windows/linux/g
```
