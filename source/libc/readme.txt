This folder contains a very tiny program which is only used for testing compiling a C program.

It can be compiled easily using gcc or clang if they are installed on Linux(or Windows if you are brave).

gcc -Wall -ansi -pedantic main.c -o main && ./main

clang -Wall -ansi -pedantic main.c -o main && ./main

In the future, I will add details about compiling with the Microsoft Visual C compiler, known as "cl".

-----

%comspec% /k "C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\VsDevCmd.bat"


By using the "where cl" command I found the location of the compiler.

C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Tools\MSVC\14.36.32532\bin\Hostx86\x86\cl.exe

----
The base program with only the C standard library can be compiled just like this.

cl main.c

Compile but rename executable:

cl main.c /Fe:test

------
SDL programs can be compiled too. The first thing to do is to make sure the right development environment is set up. This can be done by simply calling the batch file that Visual Studio installs.

"C:\Program Files\Microsoft Visual Studio\2022\Community\Common7\Tools\VsDevCmd.bat"

The following is a working compile command that works even with SDL! As long as the paths are correct and the correct SDL precompiled libraries compatible with Microsoft Visual C are in the right place, it does compile and can run!

cl main.c /IC:\msvc\sdl\include /link /LIBPATH:C:\msvc\sdl\lib SDL2.lib SDL2main.lib shell32.lib /SUBSYSTEM:CONSOLE


----

Links:

https://learn.microsoft.com/en-us/cpp/build/reference/compiler-options?view=msvc-170