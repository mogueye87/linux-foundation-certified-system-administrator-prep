# Linux Foundation Certfied SysAdmin
The Linux Foundation worked with industry experts and the Linux kernel community to identify the core domains and the critical skills, knowledge and competencies applicable to each certification. Performance-based exams were then developed based on the competencies that were identified.

## Domains & Competencies
- Essential Commands – 25%
- Operation of Running Systems – 20%
- User and Group Management – 10%
- Networking – 12%
- Service Configuration – 20%
- Storage Management – 13%

### Essential Commands – 25%

#### Searching for file Part 1 with find and locate
**Find**
- Find is use for search for files and directories
- Can search by name, file type, timestamp, and many other file attributes
- Support expressions and blobbing for advanced searches

**Locate**
- Faster search than find
- Limited search options, can not search by attributes
- Search default to the full filesystem
- Relies on database for the search, regular refresh
*
**find commanad examples**
```sh
 find -name "seach.txt"      # find command search for a file or directories in the current directory
 find / -name "search.txt"     # search for file in all the filesytem
 find /etc -name "search.txt"  # search for file in specific directory
 find /etc -iname "search.txt" # search for a file with case insensitivity
 find / -type c                # search for character
 find / -type d                # search for directory , -type -d is depreceated and is replace by -depth
 find / -type f                # search for file
 find / -type -l               # search for length 
 fins / -type f -user cloud_user # looking for a file owned by a specific user here cloud_user
```

**locate command**
> the locate command search by default to filesystem
```sh
locate "search.txt"  # search for a file in the filesystem
locate -i "search.txt" # serach for a file in the filesystem regardless the case
```

**Which**
> The which command return location of a command based on the path setting.
```sh
which command_name
which python # give the location of the python 
echo $PATH # GIVE the pathname
```

**whereis**
> This command return informations about binary, source files and man pages
```sh
whereis nano
whereis python # list binary of python and its different version
whereis python | tr " " '\n' # make the output of the whereis command more readable, tr means translate
```
**type**
> The type command return informations about the command type
> Details are based on how the command relates to the shell configuration
```sh
type python # give the location of the python
type ls # indicates that ls is the alias of "ls --color=auto"
```

#### Filesystem
> A filesystem allows to store and retrieve data on a computer (EXT4). 

#### Compare and manipulate file content, use input-output Redirection Part1- Create Files > Input-Output
**cat, less, more, sort**: commands for comparing files or directories

```sh
ls -al # lists the available files
cat filename # shows the content of the file
more  filename # shows the percentage of the file content remaining of the screen
cat filename | more # shows the content of the file one screan at the time
cat filename | less # shows the content of the file one screan at the time or line at the time
less filename
less -N filename # show file content and number of each line
sort filename # sort filename by ascending order
sort -r filename # sorting a file in the reverse order
cat filename | sort
sort filename > sorted.txt # output of the file sorted using the output redirection
touch filename # update file update access and modifications time of a file 
nano 
```

**diff**
-  compare two files or directories line by line
-  several options for ignoring, filtering the comparison

```sh
diff abortion.csv abortion2.csv # show the difference between the two files
diff -c first_filename second_filename # 
```

**comm**
- compare two sorted files line by line 
- output is displayed in 3 different columns, unique to file 1, unique twi file 2 and same in both.
```sh
comm file1 file2
```

**cmp**
- compare file byte by byte and return the position of the first difference.
```sh
cmp file1 file2
```
#### Use input-output redirection (e.g; >, >>, |, 2)
**File Descriptors**
**stdin(0)**: **Standard input**
> How data is entered or presented for processing
> Typically a keyboard or mouse or even a file

**stdin(1)**: **Standard output**
> data returned from commands

**stderr(2)**: **Standard error**
> Error messages that are returned are kept separated to stdout

**Redirection operators**
**| (pipe)**
- The pipe command is used to send output from one command to another for processing
   - cat /var/log/system.log | less

**> Create/overwrite**
- used to write ouput of a command to a file
- create a file if not exits or overwrite it if it exits
  - ls -l /etc > etclist.txt

**>> Create/append**
- used to append command output to a file
- create a file if not exists, or add output on an existing one
   - ls -l /etc >> etc.txt # write the output of a command on a file
   - wc -l filename # count the lines in a file
**< input**
- use to send input of a file to a command
- Often use to send data to a script for processing but works for command too
   - less < etc.txt 

**standard error**
> redirect the ouput of console error to a file
```sh
 cat unexistant_filename 2> error.txt # the number 2 is associated with a standard error

#### regular expressions
> Regular expression otherwise refers as regex or even regexp is a set of characters used to match search pattern

#### regular basics
^ start of a string or line
$ end of string or line
. wildcard can match any character except newline(\n)
| match a specifi character or group of character of both side (a | b a or b)
t the character t
az the string az



