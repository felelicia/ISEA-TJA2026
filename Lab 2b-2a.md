## INTRODUCTION TO BASH SCRIPTING AND SYSTEM AUTOMATION

## Lab learning overview
Basic Bash scripting and automating system tasks on Linux. 
Activities include filesystem commands, creating scripts, using loops and conditionals, and automating system monitoring tasks.

## Lab objectives
- Understand and use basic Linux commands for file management. 
- Create and execute Bash scripts. 
- Use loops and conditionals in Bash. 
- Automate basic system monitoring tasks using Bash. 
- Understand script permissions and the use of shebang (#!). 

## Part 1: Navigating the File System and Managing Files 
- Directory and File Operations Completed
  - Screenshot or terminal output of:
  - mkdir LabFiles
  - Creating notes.txt
  - Using cat, cp, mv, rm to manipulate files
<img width="534" height="63" alt="image" src="https://github.com/user-attachments/assets/6e1d9ef4-720b-4d58-bdb2-1d723f63cd8f" />
<img width="688" height="142" alt="image" src="https://github.com/user-attachments/assets/10609011-de30-4032-a08c-3971cf8b700a" />

## Part 2: Creating and Executing Basic Bash Scripts 
Example: `hello_world.sh` 
- Add `#!/bin/bash` 
- Use `echo` to display messages 
- Use `chmod 777` to make the script executable 
- Execute with `./hello_world.sh`
<img width="930" height="124" alt="image" src="https://github.com/user-attachments/assets/05aed2d4-ee1d-4a5b-91a9-012e10e6fc3a" />
<img width="570" height="83" alt="image" src="https://github.com/user-attachments/assets/c58234ef-e538-46a4-b4f3-77d684778923" />
 
## Part 3: Implementing Loops and Conditionals 
Example: `system_info.sh` 
- Use `for` loop for countdowns or iteration 
- Use `if`, `elif`, `else` to evaluate user input 
- Use `read` for interactive input 

- Loop and Conditional Script
  - Screenshot or output of system_info.sh:
  - Displays user with whoami
  - Iteration loop from 1–5
  - Input number with if-elif-else logic and validation
 
<img width="607" height="526" alt="image" src="https://github.com/user-attachments/assets/6583fb00-a84e-4912-9bd7-d3c758e2893a" />
<img width="575" height="210" alt="image" src="https://github.com/user-attachments/assets/ef40b736-dc30-49ba-aa06-d27f2b4bed15" />
 
## Part 4: Automating System Monitoring Tasks 
Example: `resource_monitor.sh` 
- Use `top`, `free -h`, `df -h` to monitor system resources 
- Use `sleep` and iteration input to control monitoring frequency

- System Monitoring Script Created and Run
  - Screenshot or terminal output of:
  - resource_monitor.sh looping through system checks:
  - top, free -h, and df -h outputs shown 
<img width="643" height="296" alt="image" src="https://github.com/user-attachments/assets/ccc5ac74-36da-47b6-a92e-065c355d99df" />
<img width="927" height="593" alt="image" src="https://github.com/user-attachments/assets/0168cb22-30bc-4d89-9ee1-a9d0e3504ffa" />

## Reflection Questions 
**What command did you use to create a new directory?**

- mkdir is used to create a new directory.
 
**How can you view the contents of a file without opening it in a GUI?**

- commands cat, less, more, can be used to view contents of a file without opening it in the GUI where they will display details of the file contents in the terminal itself.

**What is the purpose of `chmod 777`?**

- this command read, write, and execute permissions to the respective users, which allows anyone to modfiy and run the files. This must be moderated to reduce security risks since it might give unauthorised persons permission which they should not have.

**What does `#!/bin/bash` do at the start of a script?**

- this command tells the system to execute the script using Bashshell, which confirms that the script runs correctly no matter the user's default shell, preventing any external hindrance which might cause the script to run incorrectly.

**What happens when invalid input is entered into a script?**

- the script may produce an incorrect output or an ouput with errors.

**What output does `free -h` show?**

- this command displays the system memory, including total, used, free, shared, buffer, total RAM and swap memory.

**How would you monitor network bandwidth in a Bash script?**

- tools such as iftop, nload, and vnstat can be used for Bash scripts with loops or timed intervals. /proc/net/dev can also be used to read network details.
