
## Introducing the Shell - 10'

- 🎦 introduce UNIX shell using [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20UNIX%20shell%20RECORDING.pptx?d=w938c7d615eb141f0b1c0916579292cb7&csf=1&web=1&e=1AfRaI) 

- explain `$` and **text cursor**
- explain username e.g. `nelle@localhost`

## File systems - 10'
- **File browser:** demo the actions that will be covered in directory navigation using the file browser. 
    - This visual explanation should make it easier when moving to the shell.
- Explain concept of `home`
- Explain meaning of slash at the end `/`

## Navigating Files and Directories - 15'
```bash
pwd # (Print working directory)
ls –help  # (Ask for help about the 'ls' command) (Windows / Git-bash)
ls --help # another option depending on your terminal
man ls  # Show the UNIX manual page for the 'ls' command (Mac / Linux)
        # To get out use 'q' for quit
help ls # another way to see the help page
clear # Clears the terminal screen
ls      # list files
ls -l    # Long-form listing of the files in the current directory
ls -l -h  # long form with units: byte, kilobyte, etc
ls -F # for MAC 
ls --color # output color escape sequences
ls -a # list all files, including hidden files
ls -F . # . means the current directory
ls -F Desktop
ls -F Desktop/shell-lesson-data
```
Now let's move around directories
```bash
cd Desktop # Change directory to the one called "Desktop"
cd shell-lesson-data
cd exercise-data
pwd
cd shell-lesson-data # Error: no such directory
cd .. # .. means the directory above the current one
pwd
cd ~    # navigate to home directory
```

## Working with Files and Directories - 15'
- Talk about **good names for files and directories**
- Explain: create files with `touch`

```bash
pwd
cd ~/Desktop/shell-lesson-data/exercise-data/writing
ls -F
mkdir thesis
ls -F thesis # Empty directory
mkdir thesis # Directory already exists
cd thesis/
nano draft.txt # Edit the file draft.txt
touch my_file.txt # Create an empty file my_file.txt
ls
cat my_file.txt # Show the contents of a file
rm my_file.txt
ls
mv draft.txt quotes.txt # Move / rename a file
ls
cat quotes.txt
cd ..
cp thesis/quotes.txt ./quotations.txt # Copy file to a different location / name
ls
cat quotations.txt
cp -r thesis/ thesis_backup # Copy recursively – will copy folder structures
ls thesis_backup/
rm -r thesis_backup/ # !!!! CAREFUL!!! Remove contents and folder
```

## INTERMEZZO! Escape! - 5'

When we give an incomplete command to the terminal, for example we don't provide the file name to the `cat` command:

```bash
$ cat
```
Since it doesn’t have any filenames, `cat` assumes it is supposed to process input given at the command prompt, so it just sits there and waits for us to give it some data interactively. From the outside, though, all we see is it sitting there, and the command doesn’t appear to do anything.

If find yourself in this situation, **you can escape with`Ctrl+C`**.


## Using wildcards (*,?) to access multiple files - 10'
```bash
clear
cd ..
cd alkanes
ls
ls *.pdb
ls p*.pdb
ls ?ethane.pdb
ls ???ane.pdb
ls *.pdf # No such file or directory
clear
```

## Using forwarding commands - 10'

```bash
cd shell-lesson-data/exercise-data/alkanes # step into directory with .pdb files
ls                                  # confirm .pdb files are there
wc cubane.pdb                       # word count command: number of lines, words, and characters in files
wc *.pdb                        #  wc of all .pdb files in current directory + total number of lines at the bottom
wc -l *.pdb                     # only number of lines (no words/characters)
wc -l *.pdb > lengths.txt       # use > to redirect output to file

cat lengths.txt             # see content of lengths.txt
```

> IMPORTANT! Note that `>` will either create a new file or silently overwrite an existing file. Be careful

## Key points - 10'
use the cheat sheet to make sure you revise all the commands

