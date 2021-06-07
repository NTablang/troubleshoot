# Executing compiled .java files using Mac Terminal
NOTE: please open this via raw form

While I was first starting out through an IDE like Eclipse, I've tried to compile and execute .java files using the Mac Terminal.
Running it through the IDE is just perfectly fine; running it through the Mac terminal was a different story.
Through the mac terminal if you use javac <fileName>.java, it results to a successful compilation and the existence of a .class file.

Whether you're using a java version of 1.8 (aka simply '8') or higher versions of Java, running the java <fileName> command might lead to an
error saying you could not find or load main class with an error of no class exception or similar sounding errors.
  
It could either be simple errors such as typos, java and javac syntax, incorrect file name capitalization or spelling, and wrong directory.

Compiling Java (2 options):
  
(1) javac <fileName>.java
  
(2) javac /path/to/file/.java
  
Executing Java (5 options):
When executing .java files that are converted into .class files (note that .class files contain binary instructions), the main objective is to help the terminal look WHERE to look at and WHAT to look for
 
(1: The classic) java <fileName>
  
(2: Writing the Fully Qualified Name [FQN]) java package.folder.fileName

(3: Writing the Fully Qualified Name [FQN]) java package/folder/fileName

If the commands above were still unsucessful, the classpath probably could not be located by the java compiler.
This is where the cd command helps us: we explicitly tell the terminal which directory (PATH) to look for(CLASS).
I prefer to go through the directories one by one.

Suppose:
Eclipse-Workspace
  |
  |
  \- TestProject
        |
        |
        \- bin
        |   |
        |   |
        |   \- HelloWorld.class
        |
        |
        \- src
            |
            |
            \- HelloWorld.java
           
(4) This is the fourth option. 
As soon as you open the terminal (the cd default should be in /Users/):
(Also, just disregard the brackets and its contents)
>>> [Users %] cd /path/to/eclipse/workspace/folder/
>>> [eclipse-workspace %] cd TestProject
>>> [TestProject %] cd bin
>>> ls
HelloWorld.class
>>> java HelloWorld
Hello World!

(5) This is the fifth option.
As soon as you open the terminal (the cd default should be in /Users/):
(Also, just disregard the brackets and its contents)
>>> [Users %] java -cp /path/to/eclipse/workspace/folder/TestProject/bin/HelloWorld
Hello World!


Source:
https://www.youtube.com/watch?v=o08TvSyKmpk&t=131s
