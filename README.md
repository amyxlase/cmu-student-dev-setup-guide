<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 0; ALERTS: 6.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>
<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>


**Navigating the Command Line: A Primer for Incoming SCS and ECE Freshmen**

**Preamble**

Incoming CMU students in CS, ECE, and IS might not be familiar with common terminal commands that are necessary to access and complete homework in technical courses. Students will need to SSH into the AFS, GHC, and Shark machines to access the tools provided by their courses to run and test their work. They must also use terminal commands to manage and navigate through their files. Finally, particular classes will suggest debugging tools, like the python debugger and GDB, which have their unique commands. This document will cover the most common commands that incoming students may need to learn.  

**SSH to AFS, GHC cluster machines, or Shark machines through Terminal**



1. Open a terminal window on your computer. This may be called Terminal or Command Prompt depending on your operating system.
2. Your class will instruct you to connect to either the AFS server, GHC cluster machines, or Shark machines. Please execute the command for the corresponding machine. Replace &lt;andrewID> with your actual Andrew ID.
    1. AFS: **ssh &lt;andrewID>@unix.andrew.cmu.edu**
    2. GHC: **ssh &lt;andrewID>@ghc{35-42}.ghc.andrew.cmu.edu**
        1.  Replace {35-42} with any number in the range. For example, ssh andrewid@ghc35.ghc.andrew.cmu.edu
    3. Shark: **ssh &lt;andrewID>@shark.ics.cs.cmu.edu**
3. Enter your Andrew password when prompted and press Enter. After a delay, you will be connected. 

**GITHUB COMMANDS & PR REQUESTS**

Github is used as a source control tool. Students can upload their code, compare changes, and revert to specific snapshots of code. These are the basic commands that a student may need.



* git clone: Download a repository to your local machine. Any changes you make here can be automatically synced using the commands below. 
* git add: After making changes to your code, this command will add these specific changes to the staging area. This means they are ready to commit. 
* git commit -m “message”: Saves the changes from your local repository.
* git push: Syncs to your remote repository. The list of commits and their messages can be browsed like an “edit history.”
* git pull: Fetches changes from the remote repository so they can be accessed locally.
* git branch: Lists all branches in the repository. Executing git branch -a will show all branches related to your repository, including remote ones. 
* git checkout &lt;branch>: Switches to the branch that is named 
* git merge: Merges changes from one branch into another.
* git status: Shows the status of your local repository. This can be used to view your commits and changes. 

**PYTHON DEBUGGER**

To use this python debugger, import ipdb at the top of your file and place this line where you would like to stop your code:

ipdb.set_trace()

Then run your script. Your script will run until this line is executed, and it will open an interactive interface where you can view runtime variables, execute helpful debugging functions, and save the state.

C to continue

N to next

S to step

Type stuff to get their values & debug

**EXECUTING COMMON TERMINAL COMMANDS**

Most students use Windows or MacOS as their operating system, while the CMU machines all use Linux. This section provides a brief overview of commands that can be used on CMU’s machines to navigate and manage your homework files. 



1. `ls`: Lists files and directories in the current directory.
2. `cd`: Changes directory. For example, `cd &lt;directory-name>` will move to the specified directory.
    1. `cd ..: `Moves up a directory
3. `mkdir`: Creates a new directory. For example, `mkdir &lt;directory-name>` will create a new directory with the specified name.
4. `rm`: Removes a file or directory. For example, `rm &lt;file-name>` will remove the specified file.
5. `cp`: Copies a file or directory. For example, `cp &lt;source-file> &lt;destination-file>` will copy the source file to the destination file.
6. `mv`: Moves or renames a file or directory. For example, `mv &lt;old-file-name> &lt;new-file-name>` will rename the old file to the new file name, and `mv &lt;source-file> &lt;destination-directory>` will move the source file to the specified destination directory.
7. `cat`: Displays the contents of a file. For example, `cat &lt;file-name>` will display the contents of the specified file.
8. `grep`: Searches for a pattern in a file or directory. For example, `grep &lt;pattern> &lt;file-name>` will search for the specified pattern in the specified file.
9. `ln -s &lt;target> &lt;source>`: Symlink one directory with another

**SSH CONFIG**

If you have .ssh folder: 



1. Inside of ~/.ssh/config (if you already have the file), we can define SSH "shortcuts" so instead of typing, say: ssh -Y acarnegie@foo.andrew.cmu.edu, you can simply do 

    ssh cmu


If you do not have a .ssh folder, then you'll have to make one:



1. mkdir ~/.ssh
2. If you need to check if you have said folder, then run ls ~/.ssh

    Host cmu


    Hostname unix.andrew.cmu.edu


    Host ece


    ProxyCommand ssh -W %h:%p cmu


    Host ece ece.campus


    Hostname ece0XX.ece.local.cmu.edu


    Host cmu ece ece.campus


    ForwardX11 yes


    ForwardX11Trusted yes


    User $ANDREWID


**BASHRC**

The .bashrc or the .zshrc is a script file that is automatically run every time you open your shell. In this file, you can include helpful environment variables and aliases.



* To view the .bashrc: vim ~/.bashrc
* To create an alias: alias name = “cd cat/dog && conda activate env”
* To source the .bashrc: source ~/.bashrc

**Using GDB:**

GDB is a debugger for the C language that can be used to track states in your code. Here are some basic GDB commands:



1. `gdb`: Starts the GDB debugger.
2. `run`: Runs the program being debugged.
3. `break`: Sets a breakpoint at a specific line or function in the code. For example, `break &lt;line-number>` or `break &lt;function-name>`.
4. `next`: Executes the next line of code.
5. `step`: Steps into a function call.
6. `print`: Displays the value of a variable. For example, `print &lt;variable-name>`.
7. `continue`: Continues execution until the next breakpoint or the program ends.
8. `quit`: Exits the GDB debugger.

By following these steps and using these commands, you should be able to connect to the AFS and GHC SSH servers, execute common terminal commands, and use GDB for debugging. If you encounter any issues or have further questions, refer to the documentation of your specific technical course or seek assistance from your instructors or classmates.

**vim:**

Normal mode: In Normal mode, Vim is in its default state where you can navigate and manipulate text. You can move your cursor, delete, copy, paste, search, and replace text, among other operations. Normal mode is designed for efficient text editing and navigation without inserting or modifying text directly.

Insert mode: In Insert mode, you can directly input text into the file, similar to most other text editors. You can type characters, numbers, and symbols as you normally would. Insert mode is used when you want to modify text.

Command-line mode: Command-line mode is used for executing commands and performing operations that affect the entire file, such as saving changes, quitting Vim, and searching/replacing text. To enter Command-line mode from Normal mode, press the ":" key. Once in Command-line mode, you can type commands and press Enter to execute them. After executing a command, Vim returns to Normal mode.

Changing between modes / General

Esc: Exit insert mode and return to normal mode


<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: Definition &darr;&darr; outside of definition list. Missing preceding term(s)? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


:w: Save changes


<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: Definition &darr;&darr; outside of definition list. Missing preceding term(s)? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


:q: Quit (close) Vim


<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: Definition &darr;&darr; outside of definition list. Missing preceding term(s)? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


:wq or :x: Save changes and quit Vim


<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: Definition &darr;&darr; outside of definition list. Missing preceding term(s)? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


:q! or :x!: Quit Vim without saving changes


<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: Definition &darr;&darr; outside of definition list. Missing preceding term(s)? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


:w: Save changes

Normal mode navigation:

h: Move cursor left

j: Move cursor down

k: Move cursor up

l: Move cursor right

w: Move to the beginning of the next word

b: Move to the beginning of the previous word

gg: Move to the first line of the file

G: Move to the last line of the file


<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: Definition &darr;&darr; outside of definition list. Missing preceding term(s)? </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


:n: Move to a specific line number (replace "n" with the line number)

Editing:

i: Enter insert mode (insert before the cursor)

a: Enter insert mode (insert after the cursor)

o: Create a new line below the current line and enter insert mode

O: Create a new line above the current line and enter insert mode

x: Delete character under the cursor

dd: Delete the entire line

yy: Copy the entire current line

p: Paste

u: Undo the last change

Ctrl + r: Redo the last undone change
