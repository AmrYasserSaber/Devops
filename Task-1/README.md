# Devops Task 1

This task demonstrates basic file and directory operations in a Unix-like terminal.

## Steps

1. **Create a Directory**
   - Command: `mkdir Task1`
   - Description: Creates a new directory named `Task1`.

2. **Navigate into the Directory**
   - Command: `cd Task1/`
   - Description: Changes the current working directory to `Task1`.

3. **Create a File**
   - Command: `touch task`
   - Description: Creates an empty file named `task` within the `Task1` directory.

4. **List Directory Contents**
   - Command: `ls`
   - Description: Lists the contents of the current directory, which should show the `task` file.

5. **Edit the File**
   - Command: `nano task`
   - Description: Opens the `task` file in the `nano` text editor to allow for editing. In this case, the text `hello Devops` was added to the file.

6. **Display File Contents**
   - Command: `cat task`
   - Description: Outputs the contents of the `task` file to the terminal, which displays `hello Devops`.

## Example

```sh
$ mkdir Task1
```
```sh
$ cd Task1/
```
```sh
$ touch task
```
```sh
$ ls
task
```
```sh
task
```
```sh
# Add "hello Devops" and save the file
$ nano task
```
```shell
$ cat task
# hello Devops
```

