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

- Reflection: File System Commands
  - Written answers to:
  - What command did you use to create a directory?
  - How can you view file content without a GUI editor?
  - What is the difference between cp and mv? 

## Part 2: Creating and Executing Basic Bash Scripts 
Example: `hello_world.sh` 
- Add `#!/bin/bash` 
- Use `echo` to display messages 
- Use `chmod 777` to make the script executable 
- Execute with `./hello_world.sh`

- Basic Bash Script Created and Run
  - Evidence of:
  - hello_world.sh script created with #!/bin/bash and echo line
  - chmod 777 hello_world.sh
  - Output of script execution showing custom message
- Reflection: Script Basics
  - Answers to:
  - What is chmod +x for?
  - Why is #!/bin/bash used?
  - How can you personalize script output?
 
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
- Reflection: Loops and Conditionals 
  - Written responses:
  - How does the for loop work?
  - What happens if number > 10?
  - How could invalid input be handled more gracefully?
 
## Part 4: Automating System Monitoring Tasks 
Example: `resource_monitor.sh` 
- Use `top`, `free -h`, `df -h` to monitor system resources 
- Use `sleep` and iteration input to control monitoring frequency

- System Monitoring Script Created and Run
  - Screenshot or terminal output of:
  - resource_monitor.sh looping through system checks:
  - top, free -h, and df -h outputs shown 

## Reflection Questions 
- What command did you use to create a new directory? 
- How can you view the contents of a file without opening it in a GUI? 
- What is the purpose of `chmod 777`? 
- What does `#!/bin/bash` do at the start of a script? 
- What happens when invalid input is entered into a script? 

- What output does `free -h` show? 

- How would you monitor network bandwidth in a Bash script? 
