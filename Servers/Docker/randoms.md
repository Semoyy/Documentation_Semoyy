# Commandes pratiques

## Commande du Bash

Changer le hostname :
```bash
hostnamectl hostname [HOSTNAME]
```
Acceder au netplan pour la config d'IP :
```bash
sudo nano /etc/netplan/00-installer-config.yaml
```
Update system
```bash
sudo apt-get update
```
Show system and kernel
```bash
uname -a
```
Show distri­bution
```bash
head -n1 /etc/issue
```
Show mounted filesy­stems
```bash
mount
```	
Show system date
```bash
date
```	
Show uptime
```bash
uptime
```
Show your username
```bash
whoami
```	
Show manual for command
```bash
man command
```	

## Bash Shortcuts

Stop current command
```bash
CTRL-c
```	

CTRL-z
	
Sleep program
CTRL-a
	
Go to start of line
CTRL-e
	
Go to end of line
CTRL-u
	
Cut from start of line
CTRL-k
	
Cut to end of line
CTRL-r
	
Search history
!!
	
Repeat last command
!abc
	
Run last command starting with abc
!abc:p
	
Print last command starting with abc
!$
	
Last argument of previous command
ALT-.
	
Last argument of previous command
!*
	
All arguments of previous command
^abc^123
	
Run previous command, replacing abc with 123
Bash Variables
env
	
Show enviro­nment variables
echo $NAME
	
Output value of $NAME variable
export NAME=value
	
Set $NAME to value
$PATH
	
Executable search path
$HOME
	
Home directory
$SHELL
	
Current shell
IO Redire­ction
cmd < file
Input of cmd from file
cmd1 <(cmd2)
Output of cmd2 as file input to cmd1
cmd > file
Standard output (stdout) of cmd to file
cmd > /dev/null
Discard stdout of cmd
cmd >> file
Append stdout to file
cmd 2> file
Error output (stderr) of cmd to file
cmd 1>&2
stdout to same place as stderr
cmd 2>&1
stderr to same place as stdout
cmd &> file
Every output of cmd to file
cmd refers to a command.
Pipes
cmd1 | cmd2
stdout of cmd1 to cmd2
cmd1 |& cmd2
stderr of cmd1 to cmd2
Command Lists
cmd1 ; cmd2
Run cmd1 then cmd2
cmd1 && cmd2
Run cmd2 if cmd1 is successful
cmd1 || cmd2
Run cmd2 if cmd1 is not successful
cmd &
