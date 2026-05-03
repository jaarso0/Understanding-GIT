# Understanding-GIT 

Git is a version control system that keeps track of your code base. There are various VCSs, but Git stores and thinks about information in a different way. 

## The Snapshot
other VCSs keep track in the delta way, meaning they track what changed in each file over time.
v1: original file
v2: "line 5 changed from X to Y"
v3: "line 12 deleted"

where as Git takes the whole snapshot of your code base
so each time you change something, it takes its photo just for the record

okay, but isn't snapshotting going to take up much space?
well, when you commit and 10 out of 11 files didn't change, Git doesn't store 10 copies of those files gain. It just stores pointers to the already-existing copies from the last snapshot.

So memory-wise Git and SVN end up similar; storing only what changed. The difference is the mental model and the data structure.

##Things you should like about Git:
- Git needs only local files and resources to operate, the entire history of the project is right there on your local disk.
- Git is checksummed before it is stored and then referred to by the same checksum. Basically, you feed a files contents into a hashing algorithm and it spits out a fixed 40char string. So whatever you commit is ensured that is not corrupted. You do git clone so everyfile and commit is hashed and checked etc.
- Git very much only adds data, it is hard to get the system to do anything that is not undoable or to make it erase data in any way.


##Three states of Git
Git has three states and your files are in any of one: modified, staged and commited.

- modified: you changed the file but have not commited to your db yet
- staged: you have marked a modified file to go into your next commit snapshot
- commited: your data is safely stored in your local database

## The Git Directory
The Git directory is where Git stores the metadata and objects for you project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer. 

The basic Git workflow:
1. Modify files in your working tree
2. stage the changes you want to be part of you next commit
3. commit the staged changes and store the snapshot permanently in your Git directory/



references: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
