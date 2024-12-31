# Vim
Vim is command line text editor that is used to edit and create new files.

### Installation

```shell
sudo yum install vim -y
```

There are three modes in which a file can be opened i vim
1. command
2. insert
3. extended command

To create a file in vim simply navigate to the directory and write the command:
```shell
vim demofile.txt
```

This will create a file with filename `demofile.txt`, and will open it in vim editor in command mode.

### Command mode
The following commands can be executed in command mode:

![[Pasted image 20240723112349.png]]

### Extended Command mode

It is used for save and quit or save without quit using `Esc` key with `:`.
![[Pasted image 20240723112717.png]]

### Insert mode

- Also known as edit mode, is used to insert or delete lines of text from the file.
- You can enter insert mode by pressing `i` key.
- To escape insert mode simple press `Esc`, this will bring you in extended command mode.
- For saving any change type `:w` in extended command mode.
- To close vim type  `:q`.
- For saving and quit type `:wq`.