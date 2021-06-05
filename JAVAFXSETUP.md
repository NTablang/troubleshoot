# Troubleshooting setup for JAVAFX (Eclipse Mac)


Encountered this problem June 4, 2021.

Objective: Install Java FX on eclipse.

Make sure:

1.) You have a compatible java jdk version for specific java FX.
Compatibilities I've found:

[JRE] Java 1.8.291.10 = JavaFX SDK from eclipse.

This JDK from eclipse is readily and instantly available the
moment you create a javaFX project. No need for other and VM modifications.


[JRE] Java 11.0.11 =  Javafx-sdk-11.02 locally installed.

*On my computer I installed the JavaFX 11 long term support. It is locally installed either as Javafx-sdk-11.0.2 or 11.0.2.1

** This is compatible with one another with compiler compliance level 11. However, the popup event does not work.

*** If the popup event DOES work, the font is all just gibberish.

[JRE] Java 16.0.1 = JavaFX -sdk-16.2 locally installed.

*This is a multi-step process but it is doable.

2.) Installing the Java JREs (Disclaimer: I am still figuring out the difference between JDKs and JREs)
- Install your java jre desired version
- Note that pathfile to its Home. You can typically find this by going to your Mac's terminal and copy and pasting the following:
/usr/libexec/java_home -V
- Go to Help tab => Preferences => Installed JREs => Add => Standard VM => (JRE Home) Directory => <PATH/TO/YOUR/JAVA_HOME> => ADD => APPLY => APPLY and CLOSE
- New => Project (or whatever file you tryna do) => Under JRE section of the popup => Use default JRE 'HOME' and Workspace Compiler Preferences => Configure JRE
- Select your desired java version

2.) Installing the javaFX compatibles.

Just basically look through the following list and figure out what javaFX you want to download based on your .java version.
Note that for Java 16, Eclipse doesn't have a built-in support for that version. Just simply go to eclipse marketplace and install Java 16.
When creating a new project and the compiler compliance level is being displayed as a warning, just change the compiler compliance level.
Same logic aplies to Java 11 if it works on the device.

As soon as you install your JavaFX
- If you have Mac, manually download the .dylib files (via Mac Finder) one by one to bypass the Mac security issue. Failing to do so will significantly impact your program.
- Note that pathfile of the javafx lib
- On eclipse, do the following: Help tab => Preferences => User Libraries => New => Add External Jar => (go to your javafx lib folder) select all .jar files => save

3.) Configuring the build path of your project.
- Right click your file's master folder (should be the very top associated file for your project)
- Build Path => Configure build path => Libraries => (either modulepath or classpath but i think it is modulepath) remove all existing javafx folders => add library => user library => select the javafx you did earlier => add => apply => apply and continue
- At this point, all the red errors in your file should vanish. Retrace your steps if there's still error.

4.) Run configuration
- After the .java file is free of errors, hover your mouse around the green play button drop down menu on top.
- Select run configurations
- On the left hand side of the pop-up you should see an arguments tab
- On the VM argument, copy and paste the following (Mac users only and please include the two dashes in front):
--module-path <PATH/TO/JAVAFX/SDK/LIB> --add-modules javafx.controls,javafx.fxml


After that, you're basically done!!

Links of where I got help from:

[JAVAFX VERSIONS] https://gluonhq.com/products/javafx/

[JAVA 1.8 and JAVA 8 are the same thing] https://stackoverflow.com/questions/53642402/why-do-i-see-open-jdk-1-8-instead-of-java-8

[JAVA 1.8] https://www.java.com/en/download/manual.jsp

[JAVA 11] https://www.oracle.com/java/technologies/javase-jdk11-downloads.html

[JAVA 16] https://www.oracle.com/java/technologies/javase-jdk16-downloads.html

[Mac Terminal command to find Java JREs list installed] https://stackoverflow.com/questions/63654909/is-there-a-way-to-find-the-complete-list-of-java-versions-installed-on-os-x

[JAVA 16 Support on Eclipse] https://marketplace.eclipse.org/content/java-16-support-eclipse-2021-03-419

[Misc] https://openjfx.io/openjfx-docs/
