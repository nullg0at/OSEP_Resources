## Lab 2


### CTF 1: Hide the console while making a Windows System API call 
The goal of this is to hide the command prompt that pops open while making a system API call. 

Add:
```c#
//function to hide the console 
[DllImport("kernel32")]
public static extern bool FreeConsole();
```
to global scope, then make the call in the ``` Stager()``` method:
