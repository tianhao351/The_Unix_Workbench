## Unix and Command Line Basics

### 1.Hello command

- **clear** will clean up your terminal.

- ```bash
  # commands structure： 
  [command] [options] [arguments]
  ```

- You can scroll through your command history with the **Up** and **Down** arrow keys.

- **echo** prints text to your terminal.



### 2.How files and folders are organized on your computer

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/84WghVUeEeeTxBKRuWYr1A_9228b963a030e7a65deb9125aee49033_bigtree1.png?expiry=1507593600000&hmac=ft7hhHGm7rtf3uoBEJpOq3CCc2oyvMpSToJy3ImErKg)

- The directory at the top of this tree is called th **root** directory. The root directory contains all other directories, and is represented by a slash **(/)**.
- The **home** directory is another special directory that is represented by a tilde **(~)**. Your home directory contains your personal files, like your photos, documents, and the contents of your desktop. When you first open up your shell you usually start off in your home directory.
- Use the cd command to change your working directory.
- The pwd command will print the working directory.
- The ls command will list files and folders in a directory.



### 3.Creation and Inspection

-  there are a few strategies for protecting yourself from mistakes, including managing permissions for files, and tracking versions of your files with Git
- Use mkdir to create new directories.
- The touch command creates empty files.
- You can use > to redirect the output of a command into a file.
- \>> will append command output to the end of a file.
- Print a text file to the command line using cat.
- Inspect properties of a text file with wc.
- Peak at the beginning and end of a text file with headand tail.
- Scroll through a large text file with less.
- nano is simple text editor.

### 4.migration and destruction

- mv can be used for moving or renaming files or folders.
- cp can copy files or folders.
- You should try to avoid using rm which permanently removes files or folders.
- When copying (the same to rm ) folders you need to specify the -r option, which is short for *recursive*. This ensures that the underlying directory structure of the directory you wish to copy remains intact.
- In general I don’t recommend deleting files or folders on the command line because as we’ve discussed before there is **no undo button** on the command line
- The path to the Trash Bin is ~/.Trashon Mac



