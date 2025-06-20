🐧 LINUX COMMAND LINE BASICS
============================

This guide covers the basic structure of Linux commands, common file management commands, navigation, and directory tree visualization. Ideal for beginners or revision.

----------------------------------------------------
📌 COMMAND STRUCTURE

$ command --option argument

- Command: A small program that performs one task well.
- Option: Modifies how the command behaves (example: -l, -a, --help).
- Argument: The input or target the command operates on (like a file or folder name).

Example (imaginary):
$ maths --add 1 1

In most commands, both options and arguments are used to specify the operation clearly.

----------------------------------------------------
📁 LS — LIST DIRECTORY CONTENTS

$ ls

- Shows the contents of the current directory.
- Same as opening the folder manually using file managers like Dolphin, Thunar, or Nautilus.

Common Options:
- ls              → Lists visible files/folders
- ls -l           → Long listing (details: permissions, size, date)
- ls -a           → Shows all files, including hidden ones
- ls -R           → Recursively list contents of all subdirectories
- ls -Rla         → Combine all: recursive, long format, and all files

Hidden Files:
- Files that begin with a dot (.) are hidden.
- Example: `.bashrc` is hidden.
- To create a hidden file: name it starting with a dot → `.secret.txt`

List specific folder:
$ ls foldername
Example:
$ ls iterm      → Lists files inside folder "iterm"

----------------------------------------------------
📂 CD — CHANGE DIRECTORY

Used to move between directories.

Commands:
- cd /           → Go to the root directory
- cd ..          → Go back one directory level
- cd ../..       → Go back two levels
- cd "My Folder" → Use quotes if the folder name contains spaces

Note: `/` is the top (root) of the Linux filesystem.

----------------------------------------------------
📄 TOUCH — CREATE EMPTY FILES

$ touch filename

- Creates a new empty file without opening it.
Example:
$ touch notes.txt

If the file exists, it updates the timestamp.

----------------------------------------------------
📁 MKDIR — MAKE NEW DIRECTORY

$ mkdir foldername

- Creates a new folder/directory.
Example:
$ mkdir Projects

You can also create multiple folders:
$ mkdir folder1 folder2 folder3

To create parent folders recursively:
$ mkdir -p folder/subfolder/nestedfolder

----------------------------------------------------
🧹 CLEAR — CLEAR THE TERMINAL

$ clear

- Clears all previous output from the terminal screen.

----------------------------------------------------
🗑️ RM — REMOVE FILES OR FOLDERS

$ rm filename

Options:
- rm -r foldername     → Recursively delete a folder and its contents
- rm -i filename       → Ask for confirmation before deleting
- rm -f filename       → Force delete without confirmation

⚠️ Warning: Be cautious with `rm -rf` — it can delete your whole system if misused.

----------------------------------------------------
📋 CP — COPY FILES AND FOLDERS

$ cp source destination

Examples:
- Copy a file:
  $ cp file.txt ~/Documents/

- Copy a folder recursively:
  $ cp -r folder1/ ~/Documents/

----------------------------------------------------
🚚 MV — MOVE OR RENAME FILES/FOLDERS

$ mv source destination

Examples:
- Move a file to another directory:
  $ mv file.txt ~/Downloads/

- Rename a file:
  $ mv oldname.txt newname.txt

----------------------------------------------------
🌲 TREE — DISPLAY DIRECTORY STRUCTURE

$ tree

- Shows the contents of a directory in a tree-like format (branch structure).
- Starts from the current directory by default.

Examples:
- tree               → Show current directory structure
- tree foldername    → Show structure of a specific folder
- tree -a            → Include hidden files
- tree -L 2          → Show 2 levels deep only

Sample Output:
.
├── Documents
│   └── resume.pdf
├── Downloads
├── Images
│   └── summer.jpg
└── README.txt

----------------------------------------------------
✅ SUMMARY CHEAT SHEET

COMMAND         PURPOSE
-------         ----------------------------------------
ls              List files and folders
cd              Change the current directory
touch           Create a new empty file
mkdir           Make a new directory
clear           Clear terminal screen
rm              Remove file or folder
cp              Copy files or folders
mv              Move or rename files/folders
tree            Show directory structure in tree format
--option        Modify behavior of a command
argument        Specify the input/target of the command
