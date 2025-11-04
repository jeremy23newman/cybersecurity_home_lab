#Basics of Environment Variables and Set-UID Programs

## Task 1:
![UserTask1](images/task21.png)

![UserTask1](images/task21(2).png)
In this task I use different commands like printenv or env, to see the 
current environment variables I have in my machine. 

## Task 2:
![UserTask2](images/task22.png)

![UserTask1](images/task22(2).png)
This task focuses on the difference of environment variables in a parent 
and child process using the fork command. I compile the code twice, using printenv 
from the child and parent process save the output from both and compare them using the diff command.
As you can see since the diff command returns nothing the environment variables are exactly the same
between the parent and child process.


## Task 3:
![UserTask3](images/task23.png)
In this task, I compiled the myenv.c code which uses the execve command. In the first compilation the 
code prints nothing because it is not passed environ. When environ is given the code can execute properly because
environ acts as a pointer towards the environment variables in your process.


## Task 4:
![GroupTask1](images/task24.png)
Task 4 does something similar to task 3, where it prints the environment variables currently used in your process,
although the importance is the lack of safety using the system call.


## Task 5:
![GroupTask2](images/task25.png)

![UserTask1](images/task25(2).png)

![UserTask1](images/task25(3).png)
Task 5 you create a root owned set-UID program that also displays environment variables
in your process, in this example you initialize some environment variables like PATH, MYVAR, and LD_LIBRARY and check for them in your output.
I found MYVAR and PATH in my output but did not see LD_LIBRARY I do not fully understand why but I think that LD_LIBRARY being tied to dynamic linking, 
may have a reason to do with it. Since dynamic linking means the linking is done during run time.


## Task 6:
For task 6, you are supposed to use the fact that the program is set-UID and has a system call to
exploit changes you should not be able to do with a normal user. Although my installation of zsh would not work 
so I could not complete this task.

## Task 7:
![PandAList1](images/task27.png)

![UserTask1](images/task27(2).png)
Inside of this task, you explore dynamic linking more in depth. You create a sleep method that overrides the sleep method in libc
inside of the myprog code. Then compile and run myprog under different circumstances like regular program/regular user, set-UID/root/regular user,
set-UID/root/repeatLD_LIBRARY/root user and make myprog owned by a new user where the program is still set-UID, repeat the LD_LIBRARY declaration in the another user's account and then run it. In all cases where the program sleep it could have been used to exploit the machine.


## Task 8:
![UserTask1](images/task28.png)

![UserTask1](images/task28(2).png)
In task 8, you do a direct comparison between execve and system calls. Where you do an attack on the system with the code to remove a file not writable to you.
In the system call case I believe this should have been achievable due to the dangers of using a system whilst doing the same attack but with execve 
should have stopped it from happening. Although I could not test it, I believe certain parameters were stopping me from completing it and honestly I was 
not entirely sure on how it could be done.

## Task 9:
![UserTask1](images/task29.png)
In task 9 you create a "important file" called with /etc/zzz that has the permissions 0644 and the file is root owned. Then using the cap_leak.c file compiled 
into capleakprog you can use the file descriptor command in combination with the set-UID command to open a root shell even as a regular user. Which is a huge security breach.


