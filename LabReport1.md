## Lab Report 1
1) `cd` with no arguments
```
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ 
```
The working directory is `/home/lecture1/messages`.
`cd` changes directory, and when I provide no arguments, it changes to the home directory, `/home` by default.
This output is expected and not an error.

2) `cd` with path to directory
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$
```
The working directory is `/home`.
In this case, I passed in the path to the directory lecture1. This changed my directory to `/home/lecture1`.
This output is expected and not an error.

3) `cd` with path to file
```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
```
The working directory is `/home/lecture1`.
I passed in the path to the file `Hello.java`. The terminal printed out an error message that `Hello.java` is not a directory.
This is an error that occurred because `cd` changes directories. If you pass in an argument to `cd`, it should be a directory, not a file name.

4) `ls` with no arguments
```
[user@sahara ~]$ ls
lecture1
```
The working directory is `/home`.
`ls` lists the files and directories under the working directory. `/home` contains the folder lecture1, so it printed out 'lecture1'.
This output is expected and not an error.

5) `ls` with path to directory
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```
The working directory is `/home`.
I passed in the folder `lecture1`, which is contained in `/home`. `ls` then printed all the files and the folder `messages` in the `lecture1` folder.
This output is expected and not an error.

6) `ls` with path to file
```
[user@sahara ~/lecture1]$ ls Hello.java
Hello.java
```
The working directory is `/home/lecture1`.
I passed in the file name `Hello.java`, which is contained in `/home/lecture1`. `ls` then printed out `Hello.java`, because the file has no subfiles or subfolders.
This output is expected and not an error.

7) `cat` with no arguments
```
[user@sahara ~]$ cat

hi
hi
```
The working directory is `/home`.
This produced no output and clicking Enter just created a new line. This is because no arguments are passed so the terminal just waits for input. I then typed in 'hi' and it printed 'hi' back. This is because it now just echoes input until you interrupt the terminal.
This output is not an error, although I did not expect this behavior since it is different from the command's original function.

8) `cat` with path to directory
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
The working directory is `/home`.
Passing in one directory name caused `cat` to print that `lecture1` is a directory. Therefore, after passing in a directory name to `cat`, the terminal informs the user that it is a directory.
This output is expected and not an error.

9) `cat` with path to file
```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}
```
The working directory is `/lecture1`.
Passing in the file name `Hello.java` caused `cat` to print the contents of the file. `cat` will print the contents of a file if it is passed in.
This output is expected and not an error.
