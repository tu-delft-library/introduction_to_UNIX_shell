
## Tips for the day
- Make sure to plug your computer to electricity. Otherwise the display will feed electricity to the laptop and potentially turn itself off.
- Use dark marker on the board (not red)
- If you are using a mac, make the terminal not transparent: 
    - Open the terminal
    - Open settings
    - Go to background color
    - Adjust opacity to 100%


## 9:30 - Land - 5'
☕ Coffee/tea 🫖

## 9:35 - Installation check, housekeeping - 10'
- ✅ Roll call + 🤝 Code of Conduct
- 🖥 Did everyone install UNIX Shell? 
- 🖥 Did everyone download the material?
- 🙋 Getting help (🆘 red  ✅ green stickers)

## 9:45 - Icebreaker - 5'
A short icebreaker from [resources document](https://tud365.sharepoint.com/:w:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/resources.docx?d=waea671d7fc6a46d5b5c068fc19f41940&csf=1&web=1&e=f2QYgy)

## 9:50 - Introducing the Shell - 10'
> *START AUTOPUSH* 
- 🎦 introduce UNIX shell using [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20UNIX%20shell.pptx?d=waa8b334f650548598f1cf27dc80f2923&csf=1&web=1&e=RbBBDG&nav=eyJzSWQiOjI1NywiY0lkIjozNjkxODA1NTA0fQ) 
- demo how to open a shell
    - 🆘 pink/red  ✅ green wait for everyone to open shell
- explain `$` and **text cursor**
- explain username e.g. `nelle@localhost`

## 10:00 - File systems - 10'
- **File browser:** demo the actions that will be covered in directory navigation using the file browser. 
    - This visual explanation should make it easier when moving to the shell.
- Explain concept of `home`
- Explain meaning of slash at the end `/`

## 10:10 - Symbolic link to Desktop - 10'
>*NOTE TO TRAINER* Decide whether this is needed. Maybe just finding the Desktop once and staying there is enough.
- Users with Windows 10 will probably save the data in `OneDrive` Desktop.  
    - First make a symbolic link to make our lives easier.
    - `ln -s "/C:/Users/[username]/OneDrive - Delft University of Technology/Desktop" "~/Desktop"`
    - Explain **how spaces need special handling**

## 10:20 - Navigating Files and Directories - 15'
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


## 10:35 - 💪 Challenges `filedir` - 10'
>*IMPORTANT* make sure the participants open the Vevox in their laptop and type the commands in their terminal
- go to [TuDelft Vevox](https://tudelft.vevox.com/#/meetings)
- vevox 1 and 2
- start poll -> wait for answers -> discuss -> next question

#### solution 1
```bash
cd .                # No: . stands for the current directory.
cd /                # No: / stands for the root directory.
cd /home/nelle      # No: Nelle’s home directory is /Users/nelle.
cd ../..            # No: this command goes up two levels, i.e. ends in /Users.
cd ~                # Yes: ~ stands for the user’s home directory, in this case /Users/nelle.
cd home             # No: this command would navigate into a directory home in the current directory if it exists.
cd ~/data/..        # Yes: unnecessarily complicated, but correct.
cd                  # Yes: shortcut to go back to the user’s home directory.
cd ..               # Yes: goes up one level.
```

#### solution 2

```bash
../backup: No such file or directory        # No: there is a directory backup in /Users.
2012-12-01 2013-01-08 2013-01-27            # No: this is the content of Users/thing/backup, but with .., we asked for one level further up.
2012-12-01/ 2013-01-08/ 2013-01-27/         # No: see previous explanation.
original/ pnas_final/ pnas_sub/     #Yes: ../backup/ refers to /Users/backup/.
```

## 10:45 - Break - 10' 

## 10:55 - Working with Files and Directories - 15'
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

## 11:10 - INTERMEZZO! Escape! - 5'

When we give an incomplete command to the terminal, for example we don't provide the file name to the `cat` command:

```bash
$ cat
```
Since it doesn’t have any filenames, `cat` assumes it is supposed to process input given at the command prompt, so it just sits there and waits for us to give it some data interactively. From the outside, though, all we see is it sitting there, and the command doesn’t appear to do anything.

If find yourself in this situation, **you can escape with`Ctrl+C`**.


## 11:15 - 💪 Challenges `create` - 15'

- continue with the same vevox
- vevox 3, 4, 5
- start poll -> wait for answers -> discuss -> next question

#### solution 3
```bash
$ mv sucrose.dat maltose.dat ../raw
```
>Recall that `..` refers to the parent directory (i.e. one above the current directory) and that `.` refers to the current directory.

#### solution 4

>We start in the `/Users/jamie/data directory,` and create a new folder called `recombined`. The second line moves (`mv`) the file `proteins.dat` to the new folder (`recombined`). The third line makes a copy of the file we just moved. The tricky part here is where the file was copied to `.` Recall that `..` means ‘go up a level’, so the copied file is now in `/Users/jamie`. Notice that `..` is interpreted with respect to the current working directory, not with respect to the location of the file being copied. So, the only thing that will show using ls (in `/Users/jamie/data`) is the recombined folder.

```bash
proteins-saved.dat recombined   # proteins-saved.dat is at /Users/jamie
recombined                      # yes
proteins.dat recombined         # proteins.dat is at /Users/jamie/data/recombined
proteins-saved.dat              #  proteins-saved.dat is located at /Users/jamie
```


#### solution 5
The first two sets of commands achieve this objective. The first set uses relative paths to create the top-level directory before the subdirectories.

The third set of commands will give an error because the default behavior of mkdir won’t create a subdirectory of a non-existent directory: the intermediate level folders must be created first.

The fourth set of commands achieve this objective. Remember, the -p option, followed by a path of one or more directories, will cause mkdir to create any intermediate subdirectories as required.

The final set of commands generates the ‘raw’ and ‘processed’ directories at the same level as the ‘data’ directory.


## 11:25 - Using wildcards (*,?) to access multiple files - 10'
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

## 11:35 - 💪 Challenges `wildcards` - 5'

- continue with the same vevox
- vevox 6 - 7
- start poll -> wait for answers -> discuss -> next question

#### solution 6

`ls *t*ane.pdb` shows all files whose names contain zero or more characters (`*`) followed by the letter `t`, then zero or more characters (`*`) followed by `ane.pdb`. This gives `ethane.pdb methane.pdb octane.pdb pentane.pdb`

`ls *t?ne.*` shows all files whose names start with zero or more characters (`*`) followed by the letter `t`, then a single character (`?`), then `ne.` followed by zero or more characters (`*`). This will give us `octane.pdb` and `pentane.pdb` but doesn’t match anything which ends in `thane.pdb`

`ls *t??ne.pdb` fixes the problems of option 2 by matching two characters (`??`) between `t` and `ne`. This is the solution.

`ls ethane.*` only shows files starting with `ethane.`

#### solution 7

`ls NE*.txt` This command will show all the files starting in NE, followed by any number of charaters (*) and ending in .txt Not quite what we are looking for

`ls NENE01*.tx`t` This command will show all the files starting with NENE01* and ending in .txt Not quite what we are looking for. Remember: Including the extension is always a good choice!

`ls NENE01*` This command will show all the files starting with NENE01* including any extension. Not quite what we are looking for

`ls NE*A.txt` will show all the files starting with NE* followed by any number of characters (*) followed by the letter A and ending in .txt This gives the list we are looking for! Remember: Including the extension is always a good choice!

## 11:45 - Break - 10' 

## 11:55 - Using forwarding commands - 10'

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

## 12:05 - 💪 Challenges `What Does >> Mean?` - 10'

- continue with the same vevox
- vevox 7
- start poll -> wait for answers -> discuss -> next question

#### solution 7
In the first example with `>`, the string ‘hello’ is written to `testfile01.txt`, but the file gets overwritten each time we run the command.

We see from the second example that the `>>` operator also writes ‘hello’ to a file (in this case `testfile02.txt`), but appends the string to the file if it already exists (i.e. when we run it for the second time).

## 12:15 - Key points - 10'
use the cheat sheet to make sure you revise all the commands
> *TIP!* recommended to review asking participants to shout out the command :)

## 12:25 - Give feedback about the course - 5' 
Go to the link in `README.md`
