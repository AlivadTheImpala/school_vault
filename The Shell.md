| Command | Definition                                                                                                                                                     |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ls      | ls will display a list of current files in a directory                                                                                                         |
| cd      | this one will "change directory." If you only enter cd, you will be at your machines main directory                                                            |
| pwd     | shows you what your current directory is.                                                                                                                      |
| -F      | if you add -F after ls "ls -F" it will tell you the type of file you are looking at. / denotes a directory, @ denotes a link, and * denotes an executable file |
|         |                                                                                                                                                                |



 cd can only see subdirectoriess within the current director; it cant see anything above it. 



# Git Basics

## Git Syntax

git is written in the following format: **program | action | destination**

For example,

- `git add .` is read as  `git | add | .` where the period represents everything in the current directory;
- `git commit -m "message"` is read as `git | commit -m | "message"`; and
- `git status` is read as `git | status | (no destination)`.

## Basic Git Workflow
When working in your repository, eventually youll want to add your changes so that youre keeping track of your project. 

### The Staging Area
The git staging area is an area that holds all of your changes. They'll all wait here until you decided to commit them. Committing is the sum of all the changes, this is where you add a message that concisely describes the changes.

| Command    | Effect                                                                                                                          |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------- |
| git status | use this whenever you want to see the status of your local branch compared to your remote. You'll also see any untracked files. |
| git add    | use this when you want to add any files into the staging area.                                                                  |
| git commit  -m "MESSAGE GOES HERE"|   use this when you have the collection of all your changes and are ready to                                                                                                                             |






***
back to [[Index Page]]