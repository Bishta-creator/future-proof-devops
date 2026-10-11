11-10-2026
===========

##=======================VIM Editor Commands=========================================

Inserting Text
----------------
i => Inserts text before the current cursor position.
I => Inserts text at the begining of the current line.
o => Opens a new line below the current line.
O => Opens a new line above the current line.

----------------------------------------------------------------------------------
Navigating within vim
----------------------

h => Moves backward one character.
j => Moves downward one line.
k => Moves upward one line.
I => Moves forward one character.
w => Moves to the start of the next word.
b => Moves backward to the start of the preceding word.
e => Moves to the ending character of the next word.
$ => Moves to the end of the current line.
Enter => Moves to the beginning of the next line.
Ctrl+f => Scrolls down to the next page.
Ctrl+b => Scrolls up to the previous files.

----------------------------------------------------------------------------------
Deleting Text
-------------
x => Deletes the character at the cursor position.
X => Deletes the character before the cursor location.
dw => Deletes the word or part of the word to the right of the cursor location.
dd => Deletes the current line.
:6,12d => Deletes lines 6 through 12.

----------------------------------------------------------------------------------
Undoing and Repeating
---------------------
u => Undoes the previous command.
U => Undoes all the changes done on the current line.
:u => Undoes the previous last line mode command.

---------------------------------------------------------------------------------
Searching for Text
------------------
/string => Searches forward for a string.
?string => Searches backward for a string.
n => Finds the next occurrence of a string.
N => Finds the previous occurence of a string.

--------------------------------------------------------------------------------
Replacing Text
--------------

:%s/old/new => Replaces the first occurrence of old with new in a file. For example, 
replace the first occurrence of profile with Profile, use :%s/profile/Pr

:%s/old/new/g =>  Replaces all occurrences of old with new in a file. For example, to re
all the occurrences of profile with Profile in a file, use :%s/profile/Pro

------------------------------------------------------------------------------------
Copying, Moving, and Pasting Text
---------------------------------

yl => Yanks the current letter into buffer.
yw =>  Yanks the current word into buffer.
yy => Yanks  the current line into buffer.
p => Pastes yanked data below the current line.
P => Pastes yanked data above the current line

-------------------------------------------------------------------------------------
Saving and Quitting vim
-----------------------
:w => Writes changes into the file without quitting vim
:w file2 => Writes changes into a new file called file2 without quitting vim.
:w! =>  Writes changes to the file even if the file owner does not have write per
on the file.
:wq => Writes changes to the file and quits vim.
:wq! => Writes changes to the file and quits vim even if the file owner does not 
write permission on the file
:q => Quits vim if no modifications were made
:q! => Quits vim if modifications were made, but we do not wish to save them


##====================================================================================


