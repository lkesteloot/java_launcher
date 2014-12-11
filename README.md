# Java launcher

Helper script to treat Java programs as scripts.

## Overview

Put the `java_launcher` script in your path and put the following line at the
top of an executable Java source program:

    #!/usr/bin/env java_launcher

If you use Vim, add the following line:

    # vim:ft=java

Optionally add jars to compile and run with:

    # lib:/home/lk/kiln/teamten/java/dist/teamten.jar

Relative pathnames are relative to your Java script. In addition, all jars
in a `java_lib` directory below the `java_launcher` script will be included.

The source will be compiled, cached, and executed. The source file does not
need a `.java` extension, but it does need to match the name of the class.

## Example

Put this into a file called `helloworld`. The name of the file must match the
name of the class.

    #!/usr/bin/env java_launcher
    # vim:ft=java

    public class helloworld {
        public static void main(String[] args) {
            System.out.println("Hello world!");
        }
    }

Then run:

    % ./helloworld
    Hello world!

