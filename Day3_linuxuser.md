🐧 LINUX COMMAND LINE BASICS
===========================

This note summarizes essential Linux command-line concepts, syntax, and useful commands. Great for beginners or quick reviews.

----------------------------------------------------
📌 COMMAND STRUCTURE

$ command --option argument

- Command: A small program that performs one task well.
- Option: Modifies how the command behaves (like --help, -a).
- Argument: The input or target the command operates on (like a file or folder name).

Example (imaginary):
$ maths --add 1 1

Both options and arguments are often required depending on the command.

----------------------------------------------------
📁 LS — LIST DIRECTORY CONTENTS

Usage:
$ ls

This lists files and folders in the current directory.
Same as opening the folder manually in a file manager (like Dolphin, Thunar, or Nautilus).

Common Options:
- ls              → List files and folders
- ls -l           → Long format (detailed info)
- ls -a           → Show hidden files (those starting with a dot)
- ls -R           → Recursive listing (includes subdirectories)
- ls -Rla         → Combine: recursive + long + all files

Notes:
• Hidden files begin with a dot. Example: `.bashrc`
• You can create a hidden file by naming it with a dot at the start.

Listing a specific folder:
$ ls iterm     → Lists files in folder "iterm"

----------------------------------------------------
📂 CD — CHANGE DIRECTORY

$ cd /           → Move to the root directory
$ cd ..          → Move up one level
$ cd ../..       → Move up two levels
$ cd "My Folder" → Use quotes if the folder name has spaces

Note: `/` refers to the root of the Linux filesystem.

----------------------------------------------------
🌲 TREE — DISPLAY DIRECTORY STRUCTURE

$ tree

This shows the directory contents in a visual tree (branch) format.
By default, it starts from the current directory.

Examples:
- tree          → Shows all folders/files in tree view
- tree -a       → Includes hidden files
- tree -L 2     → Limit the depth to 2 levels

----------------------------------------------------
✅ QUICK SUMMARY

COMMAND         PURPOSE
-------         ------------------------------------
ls              List directory contents
cd              Change current directory
tree            Visualize folder structure in a tree view
--option        Modify behavior of the command
argument        Specify input/target for the command
