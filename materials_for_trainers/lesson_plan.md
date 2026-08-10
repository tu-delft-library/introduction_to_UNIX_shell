
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
    - Explain how **how spaces need special handling**

## 10:20 - Navigating Files and Directories - 20'
```bash
pwd # (Print working directory)
ls –help  # (Ask for help about the 'ls' command) (Windows / Git-bash)
ls --help # another option depending on your terminal
man ls  # Show the UNIX manual page for the 'ls' command (Mac / Linux)
clear # Clears the terminal screen
ls -l -h  # Long-form listing of the files in the current directory
ls -F # for MAC 
ls -F . # . means the current directory
ls -F Desktop
ls -F Desktop/shell-lesson-data
cd Desktop # Change directory to the one called "Desktop"
cd shell-lesson-data
cd exercise-data
pwd
cd shell-lesson-data # Error: no such directory
cd .. # .. means the directory above the current one
pwd
ls -a # list all files, including hidden files
cd ~
```
>*OPTIONAL*: explain permissions using `ls -color`
-rw-rw----@


## 💪 Challenges `filedir` - 10'
>*IMPORTANT* make sure the participants open the Vevox in their laptop and type the commands in their terminal
- go to [TuDelft Vevox](https://tudelft.vevox.com/#/meetings)
- vevox 1 and 2
- start poll -> wait for answers -> discuss -> next question

## Break - 10' 

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


### INTERMEZZO! Escape!

When we give an incomplete command to the terminal, for example we don't provide the file name to the `cat` command:

```bash
$ cat
```
Since it doesn’t have any filenames, `cat` assumes it is supposed to process input given at the command prompt, so it just sits there and waits for us to give it some data interactively. From the outside, though, all we see is it sitting there, and the command doesn’t appear to do anything.

If find yourself in this situation, **you can escape with`Ctrl+C`**.


## 💪 Challenges `create` - 10'

- continue with the same vevox
- vevox 3 and 4
- start poll -> wait for answers -> discuss -> next question


## XX:XX - Using wildcards (*,?) to access multiple files - 10'
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

## 💪 Challenges `wildcards` - 15'

- continue with the same vevox
- vevox 5 and 6
- start poll -> wait for answers -> discuss -> next question


## XX:XX - Using forwarding commands - 10'

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

## 💪 Challenges `What Does >> Mean?` - 10'

- continue with the same vevox
- vevox 7
- start poll -> wait for answers -> discuss -> next question

## Key points - 15'
* use the cheat sheet to make sure you revise all the commands
> *TIP!* recommended to review asking participants to shout out the command :)

## XX:XX - Give feedback about the course - 5' 
Go to the link in `README.md`
