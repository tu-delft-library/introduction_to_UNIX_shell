# Before the workshop
- Set up collaborative document 
    - [TODO] Decide if hackmd? or google docs?
- Check the slides
- Prep de vevox
    - Ask @catactg for a duplicate of the vevox material
    - Copy the share link of vevox
    - Make it a short URL using [edu.nl](edu.nl)
    - Add edu.nl QR code to slides AND copy the link on whiteboard
- Pick an icebreaker from the [resources folder](https://tud365.sharepoint.com/:w:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/resources.docx?d=waea671d7fc6a46d5b5c068fc19f41940&csf=1&web=1&e=f2QYgy)
- Practice teaching the material on your own
- [Optional] Depending on how you will visuzalise this cheat sheet (e.g. in a tablet), you might want to expoert it as a PDF

#  Introducing the Shell - 10mins
- 🎦 introduce UNIX shell using [slides](https://tud365.sharepoint.com/:p:/r/sites/ResearchDataServices/Gedeelde%20documenten/Training/Research_Software_Training/lesson_plans/resources/Introduction%20to%20UNIX%20shell.pptx?d=waa8b334f650548598f1cf27dc80f2923&csf=1&web=1&e=RbBBDG&nav=eyJzSWQiOjI1NywiY0lkIjozNjkxODA1NTA0fQ) 
- demo how to open a shell
    - ✅ wait for everyone to open shell
- explain `$` and **text cursor**
- explain username e.g. `nelle@localhost`

# Navigating Files and Directories
### File systems - 10mins
- **File browser:** demo the actions that will be covered in directory navigation using the file browser. 
    - This visual explanation should make it easier when moving to the shell.
- Explain concept of `home`
- Explain meaning of slash at the end `/`

### Symbolic link to Desktop - 10mins
[TODO] Try symlink in windows machine

- Users with Windows 10 will probably save the data in `OneDrive` Desktop.  
    - This path is very complicated, with spaces and such. 
    - Our first task will be to make a symolic link to make our lives easier.
    - `ln -s "/c/Users/[username]/OneDrive\ -\ Delft\ University\ of\ Technology\Desktop" "Desktop"`
    - **Note how spaces need special handling**

### Type along - 20mins
- pwd, ls, ls -F, ls --help, man ls, clear,cd, ., ..

```
pwd # (Print working directory)
ls –help  # (Ask for help about the 'ls' command) (Windows / Git-bash)
man ls  # Show the UNIX manual page for the 'ls' command (Mac / Linux)
clear # Clears the terminal screen
ls -l -h  # Long-form listing of the files in the current directory
ls -F # for MAC 
pwd # Print working directory
cd Desktop # Change directory to the one called "Desktop"
clear
ls
ls . # . means the current directory
ls shell-lesson-data
cd shell-lesson-data
ls
cd ..  # .. means the directory above the current one
ls -a # list all files, including hidden files
cd shell-lesson-data
cd ~
```

### Challenges `filedir` - 10mins

- go to [TuDelft Vevox](https://tudelft.vevox.com/#/meetings)
- start the poll and wait for answers
- discuss the correct answer and enable next question

# Break - 10mins

# Working with Files and Directories
- Commands: nano, cat, cp, mv, rm, mkdir, rmdir, touch
- Note: talk about **good names for files and directories**
- Explain: create files with `touch`

### Type along - 25mins

```
pwd
cd ~/Desktop/shell-lesson-data/exercise-data/writing
ls -F
mkdir thesis
ls -F thesis # empty directory
mkdir thesis # directory already exists
cd thesis/
nano draft.txt # Edit the file draft.txt
touch my_file.txt # Create an empty file my_file.txt
ls
cat my_file.txt # Show the contents of a file
rm my_file.txt
ls
mv thesis/draft.txt thesis/quotes.txt # Move / rename a file
ls thesis/
mv thesis/quotes.txt .
ls
ls thesis/
cp quotes.txt thesis/quotations.txt # Copy file to a different location / name
ls thesis/
ls
cat thesis/quotations.txt
cp -r thesis/ thesis_backup # Copy recursively – will copy folder structures
ls thesis_backup/
rm -r thesis_backup/ # Remove contents and folder
```

### Challenges `create` - 10mins

- continue with the same vevox
- start the poll and wait for answers
- discuss the correct answer and enable next question

# Using wildcards to access multiple 
- Wildcards: *, ?

### Type along - 10mins
```
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

### Challenges `wildcards` - 15mins

- continue with the same vevox
- start the poll and wait for answers
- discuss the correct answer and enable next question

# Key points -10mins
- [TODO] Better way than using slides?