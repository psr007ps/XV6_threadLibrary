# XV6_threadLibrary
Implementation of thread library in xv6 and a frisbee game

 Thread Library Implementation in XV6
● Define System Call Clone. It calls the implementation of clone function defined in proc.c
 ● A new data type to store the lock in types.h
 
 ● A thread library is created in ulib.c.Two​ pages for stack are allocated at first. If the virtual address of the start of the stack is not page-aligned, it is rounded up. Then the ​clone()​ system call is made in which, only one argument of type "unsigned int" is passed to the function, so the size is assigned to be eight. The new thread starts executing at the address specified by ​start_routine()​.
Spinlock initialization, acquire and release are defined.
 
 ● Implementation of Clone.
○ Unlike fork(), it uses parent’s address space.
○ Thread should have the same file descriptor as parent.
○ A user stack has been created to store the passed arguments and a kernel
function ​copyout() to copy ustack to the virtual address in page table pgdir. Register $esp stores the address of the top of the stack. After deciding the address of the top of the stack, register $eip is set to point to the next instruction the system is about to execute, and the base pointer register $ebp is set to be the same as $esp.
 
 ● Test program frisbee

 ● Output
○ With command frisbee 20 20
 ○ Default (with command frisbee)
 
