
                        BSD Notes by Baloi
               (!! 8 hours coding my project per week)

================================================================================

Mon Jan 26 23:10:09 EST 2015

        I will log everything I did in this file. This entry will be the main
page and all other entries will be from the newest to the oldest. If my goals
change then the main page will also change. Minimize size of main pages.

        I am creating a development machine from scratch using BSD, OpenBSD in
this case. I plan to have a good configuration for vim, Python and C development
for my needs. I need to be able to run my scheduling scripts from this machine.
I need internet from LAN at least and from wifi optimally. It would be nice to
have a nice working Gnome window manager if ever. Or I will just use tmux as my
window manager.

        Needed:
        * vim
        * good vim configuration
        * letter count in vim
        * syntax highlighting in vim
        * git?
        * internet connection           - fw_update and ifconfig solved this
        * file transfer

        If not, I will write all my tools from scratch in C and in shell script. 
        Maybe this is what I will do.
        * No internet by default.
        * No emails
        * No browser
        * Just vim
        * STUDY SOURCECODE
        * Write my own tools from scratch, even command line tools.
        * Try to use only what is in the default install plus vim and git!

================================================================================
================================================================================

Fri Apr 26 06:43:32 EDT 2024

    The Rsync algorithm in Python (to study):

    https://tylercipriani.com/blog/2017/07/09/the-rsync-algorithm-in-python/

    Change pip to pip3.12

    ?? start ??
    $ which pip3.12
    /usr/local/bin/pip3.12

    $ echo "alias pip=/usr/local/bin/pip3.12" >> ~/.bashrc
    ?? end ??

================================================================================

Tue Apr 23 13:01:05 EDT 2024

    set Ubuntu for Windows default user as root:

    ubuntu.exe config --default-user root

================================================================================

Sat Oct  1 15:22:32 EDT 2022

    Vim and Python:
    https://realpython.com/vim-and-python-a-match-made-in-heaven/

    Using mvim:
    https://dev.to/trisha114/updating-vim-macos-797
	
    Install cmake for install.py:
    $ pip3 install cmake

================================================================================

Sat Sep 10 08:07:19 EDT 2022

    Search unread messages in gmail:
    type "is:unread" in gmail search box

================================================================================

Sun Jan 16 06:34:30 EST 2022

    Using Spark web framework with Gradle:
    Add this to build.gradle

    dependencies {
        implementation 'com.sparkjava:spark-core:2.3'
    }

    Main class:
    
    public class {Your_App} { 
        public static void main(String[] args) { 
            get("/hello", (req, res) -> "Hello World"); 
        } 
    }

    $ ./gradlew run

    Go to: http://127.0.0.1:4567/hello

    Now, any file you want to read can be put in app/ directory...

================================================================================

Mon Sep  5 14:04:48 EDT 2022

    Neovim on windows init file:
    \Users\[you]\AppData\Local\nvim\init.vim

    set tabstop=4
    set softtabstop=4
    set expandtab
    set shiftwidth=4

================================================================================

Sun Jan 16 05:01:23 EST 2022

    How to add ssh keys from your machine to the remote:
    
    ssh-copy-id -i ~/.ssh/id_ed.pub root@{ip_address}

    Installing java on my remote server

    # apt-update
    # apt-install default-jre

    Whoah, 300+ mb.... I 512 mb available so what the heck anyway. I need it.

    That was done in just a few seconds too...

    # javac
    
    Command not found error...

    # apt install default-jdk

    What the heck? 200+ mb? I only have 512? Checked. 512 memory, 10 G space...
    This is a deal..

    There is a way in Debian to add path for like example install Gradle, but in 
    my Macbook, just edit ~/.bash_profile and add:

    export PATH=$PATH:/usr/local/opt/gradle/gradle-7.3.3/bin

================================================================================

Sat Jan 15 13:38:00 EST 2022

    Make sure you have gradle in path, example:
 
    $ export PATH=$PATH:/usr/local/opt/gradle/gradle-7.3.3/bin

    Make project directory

    $ mkdir web
    $ cd web

    Initialize
    $ gradle init

    Make sure package name is correct like:

    com.baloi.examples.web 
    
    run 
    
    $ ./gradlew run

    create jar
    $ ./gradlew jar

    Run jar
    $ java -jar app/build/libs/{your-app}.jar

    "No main manifest" error...

    Add to app/build.gradle

    plugins {
        id 'java'
    }

    jar {
        manifest {
            attributes (
                'Main-Class': 'com.baloi.examples.web.App'
            )
        }
    } 
    
    Run jar
    $ java -jar app/build/libs/{your-app}.jar


================================================================================
Wed Jan 12 08:29:40 EST 2022

    If you want to use something like SQLite, add this:

   <dependency>
      <groupId>org.xerial</groupId>
      <artifactId>sqlite-jdbc</artifactId>
      <version>3.7.2</version>
   </dependency>


   Then in code:
    import java.sql.*;

   And something like this:

    Connection c = null;
        
    try {
            Class.forName("org.sqlite.JDBC");
            c = DriverManager.getConnection("jdbc:sqlite:test.db");
    } catch (Exception e) {
            System.err.println(e.getClass().getName() + ": " + e.getMessage());
            System.exit(0);
    }   

    Compile and create jar

    $ mvn package

    Run 

    $ java -jar target/{your_artifact_id}.jar

================================================================================

Sun Jan  9 23:59:41 EST 2022

    This spurt of programming happened as I am recovering from my possible gout
    attack. I attribute my energy and clearheadedness from taking time off from
    work and eating probiotics from saurkraut, yogurt and overall good eating:
    > eggs and goat cheese or yogurt as a base
    > blue berries
    > cabbage and carrots
    > chicken
    Drinking lots of water!

    Archery exercises. Being out more even in the cold with my accumulated cheap
    cold weather gear (military winter boots, camo jacket surplus, cheap Chinese
    ski pants, wool socks, mittens (can be opened for fingers), base layer and
    layered upper clothing depending on temp. Once or every other week wash of
    hunting clothes with non-fragrant detergent. 

    Clear mind. Walking.

================================================================================

Sun Jan  9 12:26:16 EST 2022

    Using maven?

    ls /usr/local/opt/apache-maven-3.8.4/bin/

    export PATH=$PATH:/usr/local/opt/apache-maven-3.8.4/bin

    Make a startup script containing only the above line then:

    $ chmod 744 [yourscript]

    Permissions tutorial https://kb.iu.edu/d/abdb

    Create maven project:
    mvn archetype:generate 
	-DgroupId={project-packaging}
	-DartifactId={project-name}
	-DarchetypeArtifactId={maven-template} 
	-DinteractiveMode=false

    Taken from https://mkyong.com/maven/how-to-create-a-java-project-with-maven/

    Sample:
    mvn archetype:generate -DgroupId=com.baloi -DartifactId=baloiblog -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

    Maven templates {archetypeArtifactId}:
    https://maven.apache.org/guides/introduction/introduction-to-archetypes.html

    Go to your project directory where pom.xml is found:
    
    $ cd {project-directory}

    Update pom.xml
        <dependency> ..... </dependency>
    
    Build with:
    $ mvn package

    Errors. Java compiler..... Check java version

    $ mvn -version

Maven home: /usr/local/opt/apache-maven-3.8.4
Java version: 11.0.1, vendor: Oracle Corporation, runtime: /Library/Java/JavaVirtualMachines/openjdk-11.0.1.jdk/Contents/Home
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.13.6", arch: "x86_64", family: "mac"

    [openjdk-11.0.1.jdk]
    
    So add this to pom.xml:

<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.8.0</version>
            <configuration>
                <source>11</source> -- Using JDK 11 to compile
                <target>11</target> -- Using JDK 11 as target
            </configuration>
        </plugin>
    </plugins>
</build>

    Now works!
    
    $ mvn package

    Can't run just yet with

    $ java -jar target/{your-package}.jar

    "No main manifest."

    Add main in pom.xml

    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-shade-plugin</artifactId>
        <version>3.2.4</version>
        <configuration>
          <!-- put your configurations here -->
        </configuration>
        <executions>
          <execution>
            <phase>package</phase>
            <goals>
              <goal>shade</goal>
            </goals>

            <configuration>
                <transformers>
                    <transformer implementation="org.apache.maven.plugins.shade.resource.ManifestResourceTransformer">
                        <mainClass>com.baloi.App</mainClass>
                    </transformer>
                </transformers>
            </configuration>

          </execution>
        </executions>
      </plugin>
    </plugins>

    The use of the shade plugin allows for making an executable jar

    $ java -jar target/{your-package}.jar

================================================================================

Fri Jan  7 23:16:35 EST 2022

    Java development with a commandline build tool like Gradle...

    $ brew doctor
    $ brew update
    $ brew install gradle

    brew did not install...

    Download the gradle zip and
    $ unzip -d /usr/local/opt/gradle/ gradle-7.3.3-all.zip
    $ export PATH=$PATH:/usr/local/opt/gradle/gradle-7.3.3/bin

    Go to your project folder and 
    $ gradle init
    
    $ ./gradlew run
    $ ./gradlew test

================================================================================

Sun Jan 31 17:32:10 EST 2021

    Now using VPN and Bitdefender to make my setup a little more secure....

================================================================================

Fri Jan 29 08:07:45 EST 2021

    To install commandline tools for Mac type:

    xcode-select --install

    A software update popup will appear and you can install command line 
    developer tools.
================================================================================

Sun Jan 24 17:05:44 EST 2021

    Copy contents of id_ed25519.pub file to clipboard:

    pbcopy < ~/.ssh/id_ed25519.pub

================================================================================

Sun Jan 24 13:54:01 EST 2021

    Uninstalled Firefox and reinstalled, deleted search apps popping up, renewed
    my ssh in github. Back in business.

================================================================================

Fri Jan 22 06:55:43 EST 2021
    
    Doing my morning routine of cleaning up and getting my morning coffee with
    butter. Then notes and workout. Early mornings have helped me free up some
    time to myself then since I start work at around 10 AM, I can still make
    calls to friends and family, pay bills, call banks and figure out 
    financials. That in itself is pretty much worth it. I guess, I do a lot of
    things in the morning for life balance...

================================================================================

Mon Jan  4 11:20:07 EST 2021
    
    Just finished shoveling a couple of inches show accumulation in the driveway
    for about 45 minutes or so. Yesterday did a 30 minute kettlebell low rep
    "grooving" workout. Drank 2 glasses of water when I woke up today. Had very
    good pasta with seafood (mussels and shrimp) last night made by Julia. Have
    been drinking black coffee with butter every morning and now breakfast 
    usually. Fasting now and maybe tonight too. Definitely no coffee today.
    Monday fasting includes no coffee to reset my system every week. Got to get
    my first of the week workout Sundays to make my week go productively. And 
    one more thing: clean the kitchen or even just dishes every morning would be
    good enough as a morning routine for Task Completion (includes oral hygiene,
    making the bed, 2 glasses of salted water, take a cold ended shower).

================================================================================

Thu Dec 24 01:00:04 EST 2020
    
    Got the interactive prompt for "Building your own Lisp in C" running. I just
    needed the -ledit directive when compiling and then include only 
    editline/readline.h and not editline/history.h...

    http://www.buildyourownlisp.com/chapter4_interactive_prompt#an_interactive_prompt

    This is working....

================================================================================

Wed Dec 23 09:56:22 EST 2020

    Planning to separate this document with a blog page. Technical from 
    everything else... Thinking of processing the document to be more HTML
    friendly and changing the tag delimiters in this document with probably a
    go or a C program...
    Probably a C program as a challenge. Getting into SQLite clone source and
    learning from it.


================================================================================

Tue Dec 22 06:15:10 EST 2020

    One thing that I have learned. The time I spent configuring my environment:
    installing OS, compilation bugs - these things just bogged down the process
    and looking back, I did not produce much from those. I was reminded of the
    time one winter, when I was both installing different OS because I could not
    get an interpreted language to run with newer libraries or a compiled system
    to compile-link my program. An IDE is an idea, but I have always had this
    preference of writing things from console and vim... Well the things I have
    been coding lately have not been for production.
    Looking back, my longest streak of coding was in C.
    I have given up on some things that took too much of my time to get better
    at like chess. But it might not hurt if I keep writing, journaling, and
    coding some. This seems to be a good outlet. I do still have other things
    that I use my time for outside of family: tennis, working out, guitar, Buddy
    my dog, snow shoveling/lawn mowing, building a workout for the common man to
    be able to function well.
    I know that it has been worthwhile to do the physical activity needed for 
    lawn mowing, shoveling, cleaning up the yard - that will be my "farming"
    movements. I have had it in my mind that later in life I will have to do
    some farming-gardening to keep my body and mind working good.
    Coding/writing/journaling I think should still continue. I am learning a lot
    from looking back at what I have been doing over the past 5 or more years 
    and trying to make sense of it all..

================================================================================

Fri Dec 18 08:05:39 EST 2020

I got this line in my blockchain example program:

#include <openssl/sha.h>

Got an error compiling but was solved with this:

ln -s ../opt/openssl/include/openssl/ .

Googled:
"If you have come across this sha.h not found error on a Mac, it is because Apple dropped support for openssl."

Solved?

================================================================================

Tue Dec 15 17:35:18 EST 2020

    It is amazing how OpenBSD has the crypto libs in it already..

#include <stdio.h>
#include <crypto/ssh2.h>

struct block {
    unsigned char hash[SHA256_DIGEST_LENGTH];
    //int data;
    //struct block *link;
};

void init_ssl() {
    return;
}
int main() {
    init_ssl();
    printf("Hello there!\n");

    return 0;
}

    Now all I had to do was:
    $ gcc -o main main.c

    I did not even have to do
    gcc -o main main.c -lssl -lcrypto

    Amazing!
================================================================================

Tue Dec 17 06:29:17 EST 2019

    This is good reading for tech and how it is in a specific niche:

    http://rachelbythebay.com/w/2018/04/22/sauce

================================================================================

Mon Dec 16 09:01:41 EST 2019

    Compile multiple c files

    Messing with sqlite clone to study programming a database system from 
    scratch. Firt roadblock since I have not been programming C in a while.

    $ cc first.c main.c

================================================================================

Sun Dec 15 16:40:29 EST 2019

    Redis' first git commit:

    https://github.com/antirez/redis.git

================================================================================

Sun Dec 15 09:54:15 EST 2019

    This is a java implementation of a database system:

    http://www.cs.bc.edu/~sciore/simpledb/intro.html

================================================================================

Thu Jun  6 06:15:13 EDT 2019

    Now I have an OLD Lenovo Thinkpad running FreeBSD. It has installed:
    > Ruby
    > Python
    > Go (Yes!)
    > vim
    > git (now that computer I can use in the morning for budget and 
      programming)
    > tmux 
   
    I like the fonts of it as it has large ones (I am writing right now on my
    Mac which I changed the font on the terminal to a larger one.... Having only
    a terminal is very focusing..
    My Mac goes to Janjan when he needs it...

    The FreeBSD machine also now is a committer on my github account.

    Currently programming in Go as it makes sense. Easier to program than C in
    terms of garbage collection and pointers. Has types so less prone to errors
    from typeless languages. I did a program in python for parsing scheduling
    data. When passing data structures to functions, I do not automatically
    control what type of data structure is passed. It was easy to program fast,
    but at the same time, you have to have in your mind what a function does 
    and what it receives especially if there are many data structures. I redid
    the program in Java, which I am still fluent programming especially with an
    IDE. I did the program and it was more readable with no errors creeping in
    for incompatible types being passed to functions....
    Go is the way to go for now. I felt "power" with C, but that is a lot of
    work right there. I also like the fact that Go does not go for the OOP
    bullshit. Yes I call it BS now. Learning from mistakes, and also a talk from
    the very insightful, non-BS, creator of clojure, Rich Hickey, "Simple Made
    Easy": 
    https://www.infoq.com/presentations/Simple-Made-Easy

    I am not just yet trying to relearn Clojure right now. Golang is enough for
    now as I'll try to explore goroutines, channels and data structs in Go.
    A little bit a day....

    (15 minute rant..)

================================================================================

Wed May 29 09:45:21 EDT 2019

    Installing go on my Mac:
    $ brew install go

    Setup GOPATH ...
    Check environment vars in MAC:
    $ printenv
================================================================================

Mon May 27 15:17:41 EDT 2019

    "Simple Made Easy" talk by the creator of Clojure - Rich Hickey.

    Choose simpler stuff: choose values (immutable?), functions, neospaces,
    DATA!
    
    "Programs just manipulate data. Data is simple. The essence of the stuff -
    data. We should just manipulate the essence of the stuff."

    "Just use data"

    Polymorphism a la cart: 
    "I have data structures, I have definitions of sets of functions and I can
    connect them together" and those are 3 independent operations.

================================================================================

Mon May 27 14:41:40 EDT 2019

    It will have to be like chess right now, I have to have a balance of 
    "tactical play" and fast results and then "positional play" with very
    reliable, error resistant, but slower to build and understand (hard to 
    setup - needing a lot of forethought?)

    Gambit openings and positional openings...

    Fast and slow
    
    Think fast (split second) and think slow (code slow, build...)

================================================================================

Mon May 27 14:21:07 EDT 2019
    
    > Install python3, ipython and pip3:
    $ brew install python3
    $ pip3 install ipython 

    > install pry for ruby
    $ gem install pry

    Both pry and ipython seem to be great. I code in both so....
    I like ipython colors more (yes, it now comes to that, shiny things!)

    Funny, but Golang is supposed to be very good and made web projects in 
    ruby to golang cut server cost by 90%, response times 10X faster. 
    Javascript's 2 top devs have moved to Go 2 years ago...

    I still can't get myself to program in Go right now. Don't like the 
    compile cycle. OMG, I like instant gratification right now? Oh boy.

    I am really thinking of teaching people to setup computers that are cheap,
    have linux, ruby or python and then teach them how to program and solve
    some of their problems...

================================================================================

Tue Jan  1 10:47:33 EST 2019

    The one tool that I could use right now. My life budgetting app.

    Need to be able to:
    > calculate total expense for a period from a file
    > parse period data
    > may edit file or not
      - edit file only to write next period
    > ignore any * done * items

================================================================================

Fri Oct 19 06:15:19 EDT 2018

    Finding files in linux by name:

    $ find . -name thefile.txt

================================================================================

Fri Oct 19 06:14:31 EDT 2018

    I guess this is where I put my coding/terminal tips.

================================================================================

Sat Feb  3 12:16:30 EST 2018 (Copied from ~/journal/entries.txt)

    I am now in my coding terminal and writing in my journal.
    Just having "MMA workout" music in Spotify to keep the flow of thoughts
    going.
    Works for me.


================================================================================

Wed Jan 10 06:56:40 EST 2018

    SCons: a new kind of build tool.
    Install SCons.
    Create 'SConstruct' file:

    Program(['firstfile.c', 'otherfile.c'])

    Run:
    
    $ scons

================================================================================

Thu Jan  4 20:04:13 EST 2018

    Installing vim-go:

    $ git clone https://github.com/fatih/vim-go.git ~/.vim/pack/plugins/start/vim-go

    Then from vim:

    :GoInstallBinaries

================================================================================

Sun Dec 31 13:18:49 EST 2017

    Removing spacevim:

    Remove link .vimrc -> ~/.space-vim/init.vim
    
================================================================================

Sun Dec 17 14:40:57 EST 2017

    I can't believe that the last entry I had for learning_from repository has
    been October. I checked the git logs though and I have been commiting from
    that repo Nov 5, I and that was when I was starting to think - where do I go
    next? And then looking into code of zmq, namosg, then back to redis. Nov 7
    in Chapter1 is "build your own lisp" and just basically getting an repl 
    console without any functionality....

    Nov 8 - listTestRunner.c and then I had the segmentation fault...
    Nov 12 - listTest.c of Stanford algo samples...
    Nov 15 - Java coding using IntelliJ Idea for an MDS list page scraping...
    Nov 16 - Placing the filename in a config file...
    Those two days I was very productive with IntelliJ Idea and C...

    Nov 19 - Programming in Go using GoLand EAP from Jetbrains, it is  very nice
    but it is not free and my Early Access Program pass will end on Dec 15...

    From then on I tried programming in Go using vim with syn on but I just did
    not feel right with it... Then I just did this week for programming in Go 
    using vim: "syn off". I feel I am back again.

================================================================================

Mon Oct 30 22:27:54 EDT 2017

    My repository learning_from is growing. I am now going into TDD in C. Now
    reading the book "Test-Driven Development for Embedded C". It has a good
    example explaining the gist of TDD and using the Unity test framework for C
    testing. Enjoying it. It does say:
    > Make short succint test first, testing a very small functionality
    > Test will fail so make it pass even just with "stubs" or hardwired code.
    > Use hardwired code as long as you can, final code will come, just make
      sure that the tests are correct.
    > Do not implement code, make tests first.
    > Make tests first! Fail, success then make another test. This way your test
      will be your safety net. If you refactor, tests will show what breaks.
    > Just make your test pass, do not implement anything else...
    More of this in: https://github.com/baloi/learning_from

================================================================================

Wed Oct 25 08:31:03 EDT 2017

    I have been logging some of my work in:

    https://github.com/baloi/learning_from

    It is mostly about learning from an OSS project and learning the code or
    techniques. I did it first with the redis list data structure and the code
    really inspired me as it is not only clean and to the point but also
    reusable and it is even in heavy use in a lot of systems (as redis is used a
    lot nowadays).
    Now I am tinkering with the urlget.c code which is already teaching me a few
    things. Logging everything I do in a file does make me more productive and
    more "adventurous" - it gives me courage to make mistakes.

    Onward we go?

================================================================================

Sun Oct 22 07:01:52 EDT 2017

    Using Clojure:

    Installed lein.

================================================================================

Wed Oct 18 06:53:06 EDT 2017

    A good place for basics of algorithms and a C resource also. Based on notes 
    on Data Structures and Programming Techniques from Stanford:

    http://cs.yale.edu/homes/aspnes/classes/223/notes.html#abstractDataTypes

================================================================================

Wed Oct 11 08:03:43 EDT 2017

    Open and write to file in C (appending if file exists and creating if
    file does not exist):

    int fd;
    char *filename;
    char *buffer;
    filename = malloc(MAX_SIZE_OF_FILENAME);
    buffer = malloc(MAX_SIZE_OF_CONTENT);
    strcpy(filename, "thefile.txt");
    strcpy(buffer, "the content you want to append to file");
    // append newline
    strncat(buffer, "\n", 1);
    // open file
    fd = open(filename, O_WRONLY, O_CREAT, O_APPEND, S_IRUSR, S_IWUSR);
    if (fd == -1) error();
    if (write(fd, buffer, strlen(buffer)) == -1)
        error();
    if (close(fd) == -1)
        error();
    free(buffer);
    free(filename);

================================================================================


Tue Oct 10 08:20:45 EDT 2017

    Capstone installed:

    Download from github.

    run make.sh
    $ ./make.sh

    install
    $ sudo ./make.sh install

================================================================================

Sun Oct  8 17:30:35 EDT 2017

    Compiling multiple C programs.
    Example: main.c (has main), util.c

    $ cc -c util.c
    (produces util.o)

    $ cc util.o main.c -o main
    (produces the executable "main")

================================================================================

Sun Oct  8 13:25:26 EDT 2017

    That was a long previous post about my "study" into lists. I should not
    worry too much about the mathematical part of it, just the practical parts
    and try to incorporate it into my projects. Anyway, I am just at the part of
    implementing "elementary" data structures. Got to get the basics down and
    then build from it.

    Now here is the code that I did to test redis' adlist.c.

    list *l;
    listNode *ln;
    listIter li;
    l = listCreate();
    listAddNodeHead(l, "one");
    listAddNodeHead(l, "two");
    listRewind(l, &li);
    while((ln = listNext(&li))) {
        printf(">>%s<<\n", listNodeValue(ln));
    }
    listRelease(l);

    I checked this with valgrind:
    $ cc -g adlist_test.c
    $ valgrind --tool=memcheck --leak-check=yes -v ./a.out

================================================================================

Sun Oct  8 12:06:43 EDT 2017

    Learning through programming.

    I have on my desk (dining table) right now a copy of "Algorithms in C++,
    3rd edition" by Sedgewick with the plan to make a final implementation of
    lists in C. The plan was to incorporate the C code in "Algorithms in C" from
    O'Reily as I wanted an implementation of lists that was easier to use.
    This is how it looks like:

    List        list;
    ListElmt    *element;

    int         *data, i;

    list_init(&list, free);
    element = list_head(&list);

    //printf("list size = %d\n", list->size);
    for (i = 10; i > 0; i--) {
        if ((data = (int *)malloc(sizeof(int))) == NULL) {
            fprintf(stderr, "Error creating data\n");
            return 1;
        }
        *data = i;

        if (list_ins_next(&list, NULL, data) != 0) {
            fprintf(stderr, "Error inserting next data\n");
            return 1;
        }
    }

    I needed a more intuitive and "battle tested" list implementation. Scanned
    through the book, but then first, the implementation is in C++, second was
    that I wanted something that was used in the "real world". Came the idea:
    what would be more battle tested than a list implementation used in
    something like Doom 3. Yes! Battle tested, readable, but in C++.
    I tried searching the sources for SQLite, ZMQ ... both very nice sources,
    but I could not "free" the list implementation from the dependencies in
    their projects. BTW, SQLite and ZMQ code and the projects themselves are
    really very, very good. I used both with good results: fast, easy to use
    API and very well thought of design.
    Came Redis. Started by one developer. Now it is quite widely used in lots of
    systems (battle tested), nice code/great actually. And... I just took both
    adlist.h and adlist.c - took out the cmq dependencies (basically just the
    use of zmalloc() and zfree()) and was able to compile! The code is also very
    readable. Got to go with this!
    Anyway, I am still quite interested in Doom 3. It's use of intrusive lists
    and the game structure:

    https://gpfault.net/posts/intrusive-lists-doom3.txt.html
    http://fabiensanglard.net/doom3_bfg/DooM_Classic.php

    Which just sums it up to: I learn more by tinkering with code than reading
    from a book. Will have to spend some time to do formal study when in the
    correct mindset though... But coding is still much more fun!

    I did this whole search because of Bisqwit's youtube video about C++ for C
    programmers where he implements a list from C and improved C then C++ and
    each time the implementation gets more "readable". I have the source in
    c_me/algo/ (list.c list1.c and list2.cpp). This got me started a few months
    ago and just came back to it.

    https://www.youtube.com/watch?v=kdlIlIIHCz0

================================================================================

Sun Oct  8 10:20:20 EDT 2017

    Using spacemacs/vim is really what I want but I still have trouble with
    figuring out the basic file stuff.

    I like my vim keybindings. Will have to try editing C files with this.

    NOT. Vim it is still.

    I do not want:
    > to break my train of thought
    > to spend more time studying an editor when I can just have time to code
      a little (less than I would want)
    > to learn more search functionality, when I could just use grep, more,
      find...
    > to decrease my productivity when I have been more productive than I have
      been in a year or two

    Just sticking to Vim and C, and a little python if needed.

    No time for fluff and flashy stuff for now...

    I am also enjoying programming in C and learning through programming (more
    on the next post).

================================================================================

Fri Oct  6 22:37:29 EDT 2017

    Checking out the original git commit:

    First clone git
    $ git clone https://github.com/git/git.git

    Then checkout the version you need
    $ cd git
    $ git checkout e83c5163316f89bfbde7d9ab23ca2e25604af290

================================================================================

Thu Oct  5 11:38:56 EDT 2017

    Install iPython

    $ sudo dnf install python-devel

    $ sudo pip install ipython

    $ sudo pip install jupyter

    Jupyter is for data science stuff.

================================================================================

Sun Oct  1 11:39:13 EDT 2017

    Install ruby and ruby-gems in OpenBSD:

    # pkg_add ruby
    # pkg_add ruby-gems

================================================================================

Thu Sep 28 08:36:58 EDT 2017

    A few things I learned:
    * code snippets that are simple and named after their function are very
      useful as I use them now all the time to code my newer work - building up
      a "knowledge base" - snippets and projects/prototypes are all in the
      same directory (c_me or python_me), and are just in their own
      subdirectories.
    * include compilation process in the code or a shell script for compilation
      so you don't have to waste time and focus trying to figure out how the
      hell to compile the stuff.
    * Having a technical log like this "my_bsd_notes.txt" and keeping things
      like: setup in different OS's, firewalling, installation notes, tools and
      how to get them up an running are really VERY helpful - again it saves you
      time. These are things you need, but you really do not need to be an
      expert in (meaning you don't need to spend all your time in these areas).
    * Research just a little, build code, log and forget - free your mind to
      think of the problem at hand and be more creative. If you want to be
      "proficient" in coding, try just coding "snippets", even re-coding your
      own snippets.
    * Do other things in life. You can only do this if you are not afraid to
      lose your knowledge/skill. So code, archive and expand your knowledge.
    * Build yourself up in all aspects and that includes sleep.
    * Code in much larger font!

================================================================================

Thu Sep 28 08:25:39 EDT 2017

    I have made some progress with my client-server encryption program. Used C
    and python. I now have python-zmq app on my server, mainly using python in
    the server as libsodium in C did not compile easily and

    "I did not want to waste my time or focus"

    trying to figure out a way to make the library run. Python installation for
    both zmq and libsodium were easy on the OpenBSD server so I went with it.
    I got to practice coding the server and the client on my machine in both
    Python and C. I also was able to "debug" it just by running and seeing
    results (including just print statements at various end points). Prototyping
    was faster and more focused. No need to figure out how to setup a test
    environment. No need to study the latest testing craze. No time to waste
    time. I could spend my time on useful life stuff like tennis, working out,
    earning money through PT, cooking for my family and spending time with my
    family and dog.

    But, this is what has been done:
    > encryption test using libsodium
    > client server protypes in both C and Python (coding in both languages was
      really a kick - I will do this much more often).
    > figuring out the bare minimum of server and client and knowing the
      weaknesses of the prototypes
      * process has to be server waits and client sends out request then server
        responds
      * you cannot cut connection in between or else the server cannot accept
        the next client (it has to be a clean finish)
    > future plans:
      * include encryption (pass private keys after auth then pass encrypted
        message)
      * decrypted message will be saved in redis
      * auth process
      * "smart" server start/restart and be more robust, run even with cut
        connections.

================================================================================

Mon Sep 25 17:34:27 EDT 2017

    PF firewall:

    Load rules
    # pfctl -f /etc/pf.conf

    Show rules
    # pfctl -sr

================================================================================

Sat Sep 23 14:45:51 EDT 2017

    Developing with less pain.

    Developing for fun stays fun when you do not have to get into a couple
    of things:
    > To steep a learning curve for a technology
    > Being stuck in "configuration hell" when trying to install the tools
      you need.

    A simple example happened today. I have been able to delve a bit into
    Redis now, which is such a cool way to store data. I have done a some small
    utility programs in C which helped me learn how to use the 'hiredis' library
    which is client for redis in C. Files are in:

    ~/c_me/add_event.c
    ~/c_me/delete_event.c
    ~/c_me/edit_event.c
    ~/c_me/hiredis_test.c
    ~/c_me/list_events.c
    ~/c_me/store_and_query.c

    store_and_query.c shows the basics. I was able to figure out the C part and
    the redis part from just tutorials from redis.io... Redis: great piece of 
    code, great idea.

    Setting everything up in Fedora and learning techniques from just event the
    sample program provided in the redis source distribution was enough to get
    me started.

    Now I wanted a web front-end. In my OpenBSD server, redis was easy to
    install, hiredis I got a bunch of errors though trying to install. So I
    tried Python with Redis as I also feel comfortable with Python. The Redis
    Python client redis-py https://redislabs.com/lp/python-redis/ was also very
    easy to install in OpenBSD which had Python by default. I just had to also
    install pip first.

    Now in OpenBSD I had: Redis, redis-py (which I tested and worked), then
    uwsgi. Used uwsgi to run a 'foobar.py' that accesses redis. This is the
    run-server script:

        #!/bin/ksh
        uwsgi --fastcgi-socket 127.0.0.1:3031 --wsgi-file foobar.py --processes 4 --threads 2 --stats 127.0.0.1:9191

    Then I just edited httd.conf to listen to port 3031 on localhost to expose
    foobar.py's output through uwsgi/fastcgi:

        ext_addr="[your_ip]"
        server "localhost" {
            listen on $ext_addr port 80
            location "/foo/*" {
                fastcgi socket ":3032"
            }
        }

    Now it runs!

    Next step: send a "post" request containing the encrypted data to server
    which will be decrypted in server and saved on redis if proper credentials
    have been given.

================================================================================

Sat Sep 23 11:17:52 EDT 2017

    Sodium (NaCL encryption more readily available):

    Install in OpenBSD:
    $ sudo pkg_add libsodium

    Install in Fedora
    $ sudo dnf install libsodium libsodium-devel

    Compiling programs with <sodium.h>

    $ cc sodium_program.c -L/usr/local/lib -I/usr/local/include -lsodium

================================================================================

Wed Sep 20 19:59:29 EDT 2017

    Third post today. BTW, I am off work tomorrow, just have one homecare PT 
    eval.

    Installing pip on my OpenBSD with python 2.7.13

    # curl --remote-name https://bootstrap.pypa.io/get-pip.py

    -----------------

    Checking Redis auth/security simple:

    $ telnet [ip address] 6379

================================================================================

Wed Sep 20 19:47:19 EDT 2017

    Now that I have redis running on my OpenBSD server, the next question was:
    what project could I do? Maybe a blog? Tried installing hiredis first, but
    it had a couple of errors while building and then also the question of will
    the C program be accessible through CGI? My CGI with sqlite access did not
    work when accessed via web.
    Hmm, how about do something in between? Redis on the server and a python or
    ruby or go frontend then a C program in my local computer that just
    connects to the redis server to upload each article... Now we are talking.
    When I checked my OpenBSD server, of Ruby, Go or Python - only Python was
    installed. Good! Narrow it down and let's not deal with installation hell
    this week...

================================================================================

Wed Sep 20 16:37:02 EDT 2017

    Installing redis on OpenBSD:

    > install gmake
    $ sudo pkg_add gmake

    > go into redis-stable
    $ cd redis-stable
    $ gmake
    $ sudo gmake install


================================================================================

Tue Sep 12 23:50:24 EDT 2017

    Coding using terminal and vim works now for me with the fonts VERY LARGE...

    Solved a coding bug just having the fonts large and seeing a limited number
    of lines of code.

    Less distraction. Actually seeing the text... Maybe that is it.

================================================================================

Sun Sep 10 11:19:43 EDT 2017

    Check if ssh running:

    $ ps -ef | grep sshd

    Now run:

    $ sudo service sshd status

    $ sudo service sshd stop

    $ sudo service sshd start

================================================================================

Sat Sep  2 23:52:28 EDT 2017

    Redis install:

    $ make

    $ sudo make install

    $ sudo mkdir /usr/include/hiredis
    $ sudo cp libhiredis.so /usr/lib/
    $ sudo cp hiredis.h /usr/include/hiredis/
    $ sudo cp read.h /usr/include/hiredis/
    $ sudo cp sds.h /usr/include/hiredis/
    $ sudo ldconfig

================================================================================

Fri Sep  1 08:33:26 EDT 2017

    Revert to the latest git commit (HEAD), and delete any local changes:

    $ git reset --hard HEAD

    This will bring you back to the last commit and take out any changes
    you have made to the files.

================================================================================

Sat Aug 19 03:12:34 EDT 2017

    Using netcat as client

    $ nc <ip> <port>

    Using netcat in server mode

    $ nc -l -p <port>

================================================================================

Sat Jul 29 02:04:55 EDT 2017

    Address already in use error (when binding to port fails):

    - Find open file using tcp port:

    $ lsof -i tcp:<port>

    - Kill process
    
    $ kill -9 <PID>

================================================================================

Sun Jul 23 07:59:43 EDT 2017

    How to see in pages like wait(2):

    $ man 2 wait

================================================================================

Sun Jul 16 18:37:02 EDT 2017

        Changing nickname in irc:

        /nick [your nickname]
        /msg NickServ REGISTER password youremail@example.com
        /msg NickServ identify [your password]

================================================================================

Wed Jun 28 23:45:06 EDT 2017

    Checking log files for errors:

    # cd /var/log
    # ls -alt|head -4

    # tail messages

================================================================================

Mon Jun 19 07:14:15 EDT 2017

    Allow root to run commmands without a password using "doas":
    (http://www.tedunangst.com/flak/post/doas-mastery)

    /etc/doas.conf:

    permit :wheel
    permit nopass keepenv root

================================================================================

Sun Jun 18 21:51:45 EDT 2017

    Install vim on OpenBSD
    # echo $PKG_PATH

    # export PKG_PATH=http://ftp.openbsd.org/pub/OpenBSD/`uname -r`/packages/`arch -s`
    # echo $PKG_PATH
    # pkg_add vim

================================================================================

Sun Jun 18 21:37:44 EDT 2017

    The BCHS stack: BSD (OpenBSD, C, httpd, SQLite).

    1. Have OpenBSD (I just scratched my OS in vultr.com to OpenBSD).
    2. Have httpd. It is in OpenBSD by default. You just have to configure
       it:
       * edit /etc/httpd.conf (read previous post).
    3. Write your cgi script:
       * https://learnbchs.org/easy.html
    4. setup doas (how about just do everything):
       /etc/doas.conf

       {just empty file}

    4. setup:

        #! /bin/sh
        cc -static -g -W -Wall -o your_prog your_prog.c
        doas install -o www -g www -m 0500 cgi /var/www/cgi-bin
        doas rcctl enable slowcgi
        doas rcctl start slowcgi
        doas rcctl check slowcgi
        doas rcctl restart httpd


================================================================================

Sun Jun 18 17:09:15 EDT 2017

    Checking httpd.conf

    $ httpd -n

    A thing about /etc/httpd.conf:

    ext_addr="{your_ip}"

    server "localhost" {
        listen on $ext_addr port 80
        location "cgi-bin/*" {
            fastcgi
            root "/"
        }
    }

================================================================================

Thu Apr  6 06:39:58 EDT 2017

    Great tutorials:

    > interpreter:
    http://www.craftinginterpreters.com/scanning.html

    > Main page for learning them:
    http://viewsourcecode.org/snaptoken/

    > I was looking for this:
    http://viewsourcecode.org/snaptoken/kilo/

================================================================================

Wed Apr  5 22:11:51 EDT 2017

    Insert tab in vim:

    Ctrl-v Tab

================================================================================

Mon Apr  3 23:01:26 EDT 2017

    Install direnv Mac:

    $ brew install direnv

    Add to .profile if using bash“

    $ eval "$(direnv hook bash)"

================================================================================

Wed Mar 29 19:33:26 EDT 2017

    From : https://direnv.net/

    Setting up direnv to just have an ".envrc" in your path and not clutter the
    .profile or .bashrc.

    $ git clone https://github.com/direnv/direnv
    $ cd direnv
    $ make install

    Then add this to .bashrc:

    eval "$(direnv hook bash)"

================================================================================

Mon Mar 27 19:32:57 EDT 2017

    So CURL is supposed to:
    > make reliable data transfers with internet protocols
    > code is given away for free for anyone to use...
    > was started when Daniel Stenberg wanted to create an IRC bot for currency
      conversion, downloading updated conversion data over HTTP. He found
      "HttpGet" and Daniel had taken over the maintenance of HttpGet. Then
      functionality was added and evolved: HttpGet 1.0, urlget 2.0, curl 4.


    Internet protocols:
    > Internet Protocol (IP) is the principal communications protocol in the
      Internet Protocol Suite for relaying datagrams accross the network
      boundaries. Its routing function enables internetworking and essentially
      establishes the internet
    > IP has the task of delivering packets from the source host to the
      destination host

================================================================================

Sun Mar 26 13:26:27 EDT 2017

    Installing spacevim:

    $   sh -c "$(curl -fsSL https://raw.githubusercontent.com/liuchengxu/space-vim/master/install.sh)" 

    Inserting text from clipboard to spacevim:

    Ctrl - shift - v

================================================================================

Sat Mar  4 18:38:20 EST 2017

    Install Mosh on client (Fedora):
    $ sudo dnf install mosh 

    Install on Freebsd
    $ pkg install net/mosh

    Using mosh:

    $ mosh user@domain
    (use ssh credentials)

================================================================================

Sun Feb 26 10:53:53 EST 2017

    Going into full screen terminal:

    f11

================================================================================

Sat Feb  4 07:48:12 EST 2017

    My budgetting list in journal/budget.txt is really helping me out. I need to
    make an application to do the numbers for me though...

================================================================================

Wed Jan 18 20:46:55 EST 2017

    Check swap size in linux:

    # grep SwapTotal /proc/meminfo

================================================================================

Tue Jan 17 19:50:47 EST 2017

    Spacemacs in emacs has been driving me a little bit crazy these last few 
    days.

    I add the "line" (==============) before and after every entry. Copy and
    paste using the vim bindings goes ok. Then I have to move the cursor up with
    'k' in command mode. This just seems to delete something. I usually have to
    do a Ctrl-{ and then C-g to first enter command mode in vim then undo
    command sequences in emacs. This usually works - "usually", and usually not
    always does not work for me. Sometimes "usually" works becomes even
    "sometimes" which drives me crazy.

    Back to vim for now. I will miss space-f or finding files with C-x C-f in
    emacs which has autocomplete when looking for files. Time to find this in
    vim.

    The plus though is that even with tmux the background in vim using terminal
    in Fedora is the same background as using emacs non gui.

    Now for highlighting in vim:

    set cursorline
    hi CursorLine term=bold cterm=bold guibg=Grey40

================================================================================

Mon Jan 16 23:11:50 EST 2017

    Install sqlite development

    $ sudo yum install sqlite sqlite-devel

================================================================================

Mon Jan 16 22:37:54 EST 2017

    Emacs tips:

    > Undo    Ctrl-/ or Ctrl-u
    > Save    Ctrl-x Ctrl-s
    > Open    Ctrl-x Ctrl-f
    > Quit    Ctrl-x Ctrl-c


================================================================================

Mon Jan 16 17:58:16 EST 2017

    Installing vim on fedora properly:

    $ sudo yum update vim-minimal
    $ sudo yum install vim

================================================================================

Mon Jan 16 17:47:37 EST 2017

    Installing an rpm with "dnf" in fedora

    $ sudo dnf install *.rpm

================================================================================

Sun Jan 15 22:55:00 EST 2017

    I am now running Fedora on my Lenovo Thinkpad 450s entirely. Deleted Windows
    as I was resizing partitions and made a mess of it.

    I originally had only 7 gig for Ubuntu plus 7 gig swap. Now I have about 168
    Gig available.

================================================================================

Sun Jan 15 17:49:13 EST 2017

    Resizing panes in tmux:

    ctrl-b : resize-pane (-D, -U, -L, -R)

    Example

    ctrl-b : resize-pane -D 5  (resizes current pane downward by 5)

================================================================================

Sun Jan 15 17:41:29 EST 2017

    Install build-essential equivalent in Fedora linux:

    $ sudo yum install make automake gcc gcc-c++ kernel-devel

================================================================================

Sun Jan 15 17:17:10 EST 2017

    Generating ssh key:

    $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

    Adding your ssh key to the ssh-agent:

    $ eval "$(ssh-agent -s)"

================================================================================

Sun Jan 15 11:25:52 EST 2017

> hibernate.sh:

sudo pm-hibernate

> net-restart

#! /bin/sh
sudo service network-manager restart

================================================================================

Sun Jan 15 11:24:15 EST 2017

> preparing thinkpad for battery saving

https://itsfoss.com/reduce-overheating-laptops-linux/

http://www.webupd8.org/2014/04/prevent-your-laptop-from-overheating.html


================================================================================

Wed Jan 11 22:20:55 EST 2017

    How do I get rid of the ugly green h-line in emacs when run in terminal or
    terminator? I need fullscreen or something like that which would have split
    panes with editor(s) and at least one terminal.

    Now if I could only find a solution, it would really make life much better.

    It would actually make life the best!

================================================================================

Mon Dec 26 21:45:13 EST 2016

    What would really be nice to work on nowadays.
    > C programming
    > TLS, encryption schemes using mbed TLS

================================================================================

Sun Dec 18 22:06:07 EST 2016

    Having multiple terminals filling up the screen is how I am working right
    now. Gives me a view of four things that I may be working at once. Not using
    tmux for now as I am using emacs and tmux changes the look (font, background
    and highlighting. Spacemacs is a comfortable and pleasing environment to
    work on. I've got some basic shortcuts down and the vim bindings for editing
    just work. Quite a workable setup.
    Installing spacemacs just involved installing a newer version of emacs and
    then just downloading the spacemacs configuration:

    $ git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d

    Then on first run, spacemacs asks for defaults. I chose the vim bindings
    with it and then it just works!

================================================================================

Sun Dec 18 12:31:42 EST 2016

    Running shellcode example:

    int main() {
        unsigned char code[] = "\x45\x31\xd2.....";
        void (*ret) () = (void(*)()) code;
        ret();
        // ( *( void( * ) ()) code) ();
    }

    compile with:

    $ gcc -z execstack test_shellcode.c -o test_shellcode
================================================================================

Sun Dec 18 11:39:36 EST 2016

    Using pry:

    $ sudo gem install pry
    $ pry

    pry(main)> s="something"
    pry(main)> show-doc s 

    pry(main)> ls 

    Can use 'ls', 'cd', 'gem-cd'
    'nesting' shows where you are: use '..' to get out of that context

    How to use screencast found here:

    http://pryrepl.org/ (used SHIFT-middle_mouse in linux to paste)

================================================================================

Sun Dec 18 09:35:56 EST 2016

    Adding shell command output to buffer in spacemacs:

    SPC-u SPC-! [shell command]

    In emacs it is

    C-u M-x ! [shell command]

    But C-u does not work in my installation of spacemacs.


================================================================================

Sun Dec 18 09:22:16 EST 2016

    Studying snippets from the book "The Practice of Programming" by Kernigan
    and Pike. Had trouble making lookup function work, but finally did:

    int lookup (char *word, char *array[]) {
        int i;
        for (i = 0; array[i] != NULL; i++) {
            if (strcmp (word, array[i]) == 0) {
               return i;
            }
        }
        return -1;
    }

    use like:

    char *flab[] = {"something", "another", "aword", NULL}; // NULL terminate
    int found = lookup (word, flab);

================================================================================

Wed Dec 14 22:18:16 EST 2016

    Emacs/spacemacs is really working out right now. I do not care for learning
    too much new editing keys. I just like the font, the background and the
    directory opening. So far it works for me. Let us see more what will happen.

    Eye candy is winning me over.

    And org mode in emacs look very slick.

================================================================================

Wed Dec 14 07:36:16 EST 2016

    Starting emacs in terminal (no window):

    $ emacs -nw

    I am a little bit getting the hang of using spacemacs. My vim keys work (the
    little that I know). I like the screen contrast and the font itself which is
    very comfortable. This itself is a reason enough to learn some emacs and
    keep my old keybindings. Opening files is also easy with spacemacs:

    SPC - f - j

    which opens dired and you can navigate with 'kl' vim navigation keys.

    Also this same display is consistent in my FreeBSD remote server which has
    I log into with ssh.

    Things I need to figure out:
    > inserting shell command output in current buffer (like date)
    > adjusting shiftwidth/tabstop to 4 characters
    > better autocomplete for C code.

    And I can even split windows easily with SPC - w - and then navigate windows
    with vim keybindings (Ctrl-w [hjkl]). Sold!

    Another caveat. The contrast and line highlight changes if emacs is run
    under tmux.

================================================================================

Tue Dec 13 23:19:16 EST 2016

    Disable syntax hightlighting in emacs:

    M-x font-lock-mode

    Print date and time on current emacs buffer (write shell command result):

    C-u M-! [command]


================================================================================

Sun Nov 27 09:26:21 EST 2016

    I have been delving into assembly language this week since middle of the
    week. Bought the book HTAOE (Hacking the Art of Exploitation). It has some
    examples of disassembling programs in gdb. A lot of C coding. Back to basics
    and really studying how it all works. Sweet! This seems to be worth at least
    a month's study in itself.

    Started with a tutorial in asm compiling with "as", but got go find one in
    "nasm". Tried coding in Linux and FreeBSD. The linux sample puts values in
    registers (edx, ecx, ebx) and FreeBSD sample does "push dword val" right 
    away. Both call 'mov eax, syscall' and then 'int 0x80' to call kernell.
    The '.data' section both have the strings "stringname db 'the string'".

    Here is an example code (any text proceeding ';' are ignored)

; hello.asm
; compile with:
; nasm -f elf hello.asm (add -g option for debug)
; ld -m elf_i386 -s -o hello hello.o (remove -s option for debug)

section .data
    msg db 'Hello ,world na!', 0xa ; string to be printed
    len equ $-msg
section .text
    global _start
_start:
    mov     edx, len
    mov     ecx, msg
    mov     ebx, 1      ; file descriptor for stdout is 1
    mov     eax, 4      ; system call (write)
    int     80h         ; call kernel  "int 0x80" (would work too)

    mov     eax, 1      ; sytem call (exit)
    int     0x80

================================================================================

Sat Nov 26 20:40:35 EST 2016

    Tinkering with assembly language programming. Using nasm to compile and then
    ld. Works in linux. Going to try on my Mac what goes...

================================================================================

Wed Nov 23 07:50:08 EST 2016

    Lint in linux

    $ sudo apt-get install splint

    $ splint anything.c

    This will do a static code analysis.

================================================================================

Sat Nov 19 07:58:55 EST 2016

    Install py-supervisord to monitor web application and restart it if needed:

    # pkg py-supervisord

================================================================================

Fri Nov 18 23:08:14 EST 2016

    Getting nginx running.

    Install

    # pkg install nginx

    Configure autostart
    
      - edit /etc/rc.conf
      - add nginx_enable="YES"

    Start nginx

    # service nginx start 

    or

    # service nginx onestart

    Can be configured: /usr/local/etc/nginx/
    Default pages: /usr/local/www/nginx/

================================================================================

Fri Nov 18 20:04:01 EST 2016

    Installing vim-lite for less dependencies (2 instead of 72 in FreeBSD):

    # pkg install vim-lite

================================================================================

Fri Nov 18 19:41:28 EST 2016

    Preparing pkg package management in FreeBSD

    Bootstrap system:

    # /usr/sbin/pkg

================================================================================

Fri Nov 18 13:01:11 EST 2016

    Install pip on FreeBSD and then Flask:

    # python -m ensurepip

    Upgrade pip
    # pip install --upgrade pip 

    # pip install flask

================================================================================

Fri Nov 18 07:50:07 EST 2016

    Installing a port
    # cd /usr/ports/<category>/<portname>
    # make install && make clean


    Uninstall:
    # cd /usr/ports/<category>/<portname>
    # make deinstall

================================================================================

Fri Nov 18 07:56:07 EST 2016

    Update ports
    # portsnap fetch
    # portsnap extract

    After above has been done, /usr/ports can be upgraded as needed by:
    # portsnap fetch
    # portsnap update
    

================================================================================

Fri Nov 18 00:44:11 EST 2016

    And also when coding, always have music on... Metal preferrably.

================================================================================

Thu Nov 17 23:19:34 EST 2016

    Coming to think of it. If I have a weekend available, I might consider 
    hosting a text blog on a FreeBSD server... Hosted on a cheaper host (below
    $10) monthly.
    Got to go back to zeromq and C coding the rc4 thing.

================================================================================

Thu Nov 17 23:06:23 EST 2016

    I will put down firewall and tcpdump tinkering for now and go back to 
    writing and coding every day. That was a nice off time, but have to keep
    focused on what I do though... Which are coding, writing and living a full
    life. I almost shutdown my linode account for an NQ hosting as I was really
    intrigued by an article regarding Linux or FreeBSD servers. But, I know that
    after getting the server up, I am not the type to keep asking support. Or
    maybe it will be worth it. Anyway, FreeBSD on a laptop, Linux on my main
    machine and may switch to FreeBSD hosting as soon as I figure out the 
    payment method I want to do. I just feel that I don't want to spend time at
    this time learning how to keep another new server, now in FreeBSD, can be
    kept secure without eating up my whole nights - sleep is also another thing
    I value these times.
    
================================================================================

Thu Nov 17 22:48:43 EST 2016
    
    And oh, I forgot to mention - I just ditched my OpenBSD installation... Just
    did it a couple of days ago. Replacing it is FreeBSD. I decided on FreeBSD
    due to an itch to play with firewalls, namely IPFW, but did not go too deep
    into it. It took me three installation tries with FreeBSD excluding trying
    to find the correct BSD image for my machine and writing the image on a USB
    stick. I first wrote the image from windows, but I had used a 64-bit image,
    forgetting that I had an old machine. Downloaded the i386 one and wrote it
    again from windows a couple of times but this time the usb stick would not
    boot properly. Considered using my Mac to write the image but that would
    again entail "researching" the right commands... Maybe it is in this file 
    though... Yes it is here somewhere, but to save on time (which is a very
    important commodity nowadays to be able to enjoy life more), I decided to
    just write the image with "dd" in Linux... And it worked like a charm. Sort
    of.

    What happened next was 3 installation tries. As being the impatient me, I
    would move my laptop around while the installation was going on and then an
    error would occur. I understood this so the third time, I did not move the
    laptop during the install process at all (I had the thought that some
    laptops are build like superman). But I did have a couple of surprises
    with this FreeBSD install.

    > The startup screen had nice contrasting fonts in white/gray.
    > Wifi was configured during install without a hitch.
    > Close the laptop lid, open it again and everything works again, even
      wifi.
    > The installation fit the 40 gig hardrive easily - 8% used only even after
      tmux, vim, python, ruby and all other dependencies were installed.
    > Vim has the "dropdown" list for intellisense.
    > Vim has the C lib tagged already.
    > Running a couple of days without restarts, although I do close the lid...
    > Easy to install software. 
    > Just works fine.
    
================================================================================

Mon Dec  5 21:52:45 EST 2016

    Get list of subfolders sorter by their size

    du --max-depth=1 /home/yourdir/ | sort -n -r

================================================================================

Wed Nov 16 22:33:58 EST 2016

    Add user in BSD with su privs:

    # adduser

      -> then invite to group "wheel"

    Install something like tmux:

    # cd /usr/ports/sysutils/tmux/
    # make install clean
    # rehash

================================================================================

Wed Nov 16 21:26:41 EST 2016

    How to prepare a usb stick as installation media for FreeBSD from Linux

    Find usb stick dev name from linux commandline:

    # ls -l /dev/disk/by-id/usb*

    And then write a FreeBSD*.img to it:

    # dd if=FreeBSD-11.0-RELEASE-i386-memstick.img of=/dev/sdc bs=1M conv=sync

================================================================================

Wed Nov 16 13:03:53 EST 2016

    Reading pflogs http://man.openbsd.org/pflogd

    # tcpdump -n -e -ttt -r /var/log/pflog

    In realtime
    
    # tcpdump -n -e -ttt -i pflog0

================================================================================

Mon Nov 14 22:22:59 EST 2016

    Just finished the C practice code for sqlite inserts. Found a page that
    explains how to make really fast inserts - starting from the worst case
    scenario of about 85 inserts per second to 96,700 inserts per second.


================================================================================

Sun Nov 13 17:20:52 EST 2016

    Checking IP:

    $ wget http://ipinfo.io/ip -qO -

================================================================================

Sun Nov 13 16:59:59 EST 2016

    $ expressvpn activate
    $ expressvpn connect United\ States
    $ expressvpn disconnect

================================================================================

Sun Nov  6 17:01:36 EST 2016

    Hibernating in Ubuntu:

    $ sudo pm-hibernate

================================================================================

Sun Nov  6 16:37:51 EST 2016

    I have now installed Linux (Ubuntu distro) on my Lenovo Thinkpad. Instead of
    trying to buy a Raspberry Pi or use my Mac as the development machine/server
    it was easy to just use one of the partitions in my Lenovo as the Ubuntu
    drive...

    Anyway, for zeromq which I have been struggling with for 2 days and not
    being able to code much because of just trying to configure it to run in
    gcc tdm in windows, cygwin on windows or even a visual studio project which
    was the only one that compiled, but crashed anyway. No more of that
    nonsense!

    Downloaded Posix sources for zeromq, untarred, ./configure, make, make
    install and whala! It is running.

    I even have vim running, git now setup with keys of this machine for my 
    github page, vimrc updated from my Windows setup and enjoying coding without
    syntax highlighting.

    Now back to that snippet. One snippet a day at least...
================================================================================

Sun, Nov 06, 2016  4:15:30 PM

    Some contents of my vimrc:

" baloi start
set history=10000
set expandtab
set tabstop=4
set shiftwidth=4
set softtabstop=4
set autoindent
set laststatus=2
set showmatch
set incsearch
set hlsearch
" make searches case-sensitive only if they contain upper-case characters
set ignorecase smartcase
" highlight current line
set cursorline
set cmdheight=1
set switchbuf=useopen
" Always show tab bar at the top
set showtabline=2
set winwidth=79
" Don't make backups at all
set nobackup
set nowritebackup
set backupdir=~/.vim-tmp,~/.tmp,~/tmp,/var/tmp,/tmp
set directory=~/.vim-tmp,~/.tmp,~/tmp,/var/tmp,/tmp

syntax on
" use emacs-style tab completion when selecting files, etc
set wildmode=longest,list
" make tab completion for files/buffers act like bash
set wildmenu
let mapleader=","
" Fix slow O inserts
:set timeout timeoutlen=1000 ttimeoutlen=100
" Turn folding off for real, hopefully
set foldmethod=manual
set nofoldenable
" Insert only one space when joining lines that contain sentence-terminating
" punctuation like `.`.
set nojoinspaces
" If a file is changed outside of vim, automatically reload it without asking
set autoread
" Use the old vim regex engine (version 1, as opposed to version 2, which was
" introduced in Vim 7.3.969). The Ruby syntax highlighting is significantly
" slower with the new regex engine.
set re=1

""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" COLOR
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
:set t_Co=256 " 256 colors
:set background=dark
:color grb256

""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" STATUS LINE
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
:set statusline=%<%f\ (%{&ft})\ %-4(%m%)%=%-19(%3l,%02c%03V%)
" baloi end

================================================================================

Thu, Nov 03, 2016  9:57:32 PM

    I was off on Monday so I was able to figure out how to setup and code basic
    things in SDL. I was just at the library before dinner and read advice 
    somewhere saying that you should just code all the time - or it was put as
    don't stop coding. It is the way to be continually able to fluently code.
    It did not say read, study or copy code. Just write code.

    Everyday I have to code. If I want to code something that I do not know how
    to then I will read a little and try to code it myself again, until I have
    a solution. These should then be just small snippets to be doeable and not
    too difficult as to get me stuck in coding paralysis.

================================================================================

Mon, Oct 31, 2016  8:16:12 PM

    Code I used, structured with C++ style structures (different from C as the
    C++ struct can have methods). This is a style I got from Bisqwit -

    https://www.youtube.com/watch?v=kdlIlIIHCz0 
    (C++ for C programmers-Lesson1)

    This program now compiles and runs properly.

-------- CODE START -----------
/* window.cpp */
#include <SDL.h>
#include <stdio.h>

struct AG_Game {
    static const int WinWidth = 1024;
    static const int WinHeight = 768;
    SDL_Window  * Window = NULL;
    SDL_Renderer * Renderer = NULL;
    SDL_Surface * PrimarySurface = NULL;

    void Cleanup() {
        if (Renderer) { SDL_DestroyRenderer(Renderer); Renderer = NULL; }
        if (Window) { SDL_DestroyWindow(Window); Window = NULL; }
    }

    void OnEvent(SDL_Event * Event) {
        /* code here */
    }

    void Loop() {
        /* code here */
    }

    void Render() {
        SDL_RenderClear(Renderer);
        SDL_RenderPresent(Renderer);
    }

    bool Init() {
        if(SDL_Init(SDL_INIT_VIDEO) < 0) { fprintf(stderr, "Unable to Init SDL: %s", SDL_GetError()); return false; }
        if(!SDL_SetHint(SDL_HINT_RENDER_SCALE_QUALITY, "1")) { printf("Unable to Init hinting: %s", SDL_GetError()); }
        if((Window = SDL_CreateWindow("AG_Game", SDL_WINDOWPOS_UNDEFINED, 
                        SDL_WINDOWPOS_UNDEFINED, WinWidth, WinHeight, SDL_WINDOW_SHOWN)) == NULL) {
            fprintf(stderr, "Unable to create SDL Window: %s", SDL_GetError()); return false; 
        }
        PrimarySurface = SDL_GetWindowSurface(Window); 
        if((Renderer = SDL_CreateRenderer(Window, -1, SDL_RENDERER_ACCELERATED)) == NULL) { 
            fprintf(stderr, "Unable to create renderer"); return false; 
        }
        SDL_SetRenderDrawColor(Renderer, 0x00, 0x00, 0x00, 0xFF);
        return true;
    }
};

int main(int argc, char * argv[]) {
    bool Quit = false;
    AG_Game game;

    if(!game.Init()) 
        fprintf(stderr, "Unable to Initialize game\n");

    SDL_Event Event;
    while(!Quit) {
        while(SDL_PollEvent(&Event) != 0) {
            game.OnEvent(&Event); // User defined event-handling
            if(Event.type == SDL_QUIT) Quit = true;
        }
        game.Loop();     // User loop
        game.Render();   // Now we render

        SDL_Delay(1); // Breath
    }
    game.Cleanup();
    return 0;
}

-------- CODE END   -----------

compile.bat:

g++ window.cpp   \
-IC:\cygwin64\home\coder\libs\SDL2-2.0.5\x86_64-w64-mingw32\include\SDL2   \
-LC:\cygwin64\home\coder\libs\SDL2-2.0.5\x86_64-w64-mingw32\lib -w         \
-Wl,-subsystem,windows -lmingw32 -lSDL2main -lSDL2 -o window

================================================================================

Mon, Oct 31, 2016  8:01:22 PM

    Spend the whole day tinkering first with SFML on windows trying to get it
    set up. Could not make it link properly using TDM Gcc toolset for Unix like
    gcc and the like. Spent almost an hour and kept looking through google. I
    even connected to the irc channel and maybe muster the courage to ask, but
    never did. Not even familiar enough of irc etiquette. Gave up and then 
    decided to try SDL. 
    This tutorial helped me with the setup:

    http://lazyfoo.net/tutorials/SDL/01_hello_SDL/windows/mingw/index.php

    The compile command used was:

    g++ 01_hello_SDL.cpp -IC:\mingw_dev_lib\include\SDL2
    -LC:\mingw_dev_lib\lib -w -Wl,-subsystem,windows -lmingw32 -lSDL2main
    -lSDL2 -o 01_hello_SDL

    But that did not work for me so I used this one: 


    g++ board.cpp   \
    -IC:\cygwin64\home\coder\libs\SDL2-2.0.5\x86_64-w64-mingw32\include\SDL2 \
    -LC:\cygwin64\home\coder\libs\SDL2-2.0.5\x86_64-w64-mingw32\lib -w       \
    -Wl,-subsystem,windows -lmingw32 -lSDL2main -lSDL2 -o board

    Of course I used different paths for includes and libraries.

    The sample code in the site did crash though, although it did compile and 
    run.
    
    Code to follow...

================================================================================

Sat, Oct 29, 2016  5:10:04 PM

    I opened my old Macbook last night and charged it after doing a little bit 
    of late night surfing. I've destroyed the USB wireless from use as it jutt
    out a little bit to the side of the mac, but miraculously, the wireless is
    now working again. I put it in a corner of the room turned of and when I
    started it, it just did and still a fast boot time. My main machine now is
    this Lenovo Thinkpad T450s with Cygwin installed as I got tired of using
    Windows command line tools. Unix like always works.

    Fullscreen iTerm with vim just looks much better. Keyboard is not like the 
    Thinkpad, but also very good - both are. Got to fix that part of it - fonts
    and even the colorscheme. But still, the Macbook for development kicks ass.

    Fullscreen iTerm in the Mac though is distraction free.    

    I just bought the Lenovo as it was getting harder to install newer software
    on my old Mac. 

================================================================================

Sun, Oct 23, 2016  8:04:47 AM

    I can't believe how slow my machine runs Go programs for the first time. A
    simple "hello world" application actually took about 10 seconds to start and
    print. A similar program in C took less than a second to compile and then
    even less to run. Even a similar program in Ruby took about to a second or
    less to run. 

    Why?

    I am using Cygwin under windows right now, but I have had the same problem
    in my Go installation in Windows. I used Visual Studio "cl" for C and the
    Ruby installation from ruby-lang.org. In Cygwin, Go, gcc, and Ruby were all
    installed by default (I did check a few more options during the install
    process).

    This is the reason why I left Go. I know, I may seem to be such a demanding
    programmer. But, I program only in my free time to "relax" myself. I like
    using console tools. I do like to idea of Go being able to compile it and it
    has a lot of things going for it like much simpler syntax than C, easy net-
    working, concurrency, go tools... Not to mention built by Rob Pike and Ken
    Thompson.

    I have to say though that after the first run or compile, the Go program 
    runs much faster. In my Mac installation it also is a little bit faster
    even on the first run.

    But here is the thing. When I develop, I edit in vim, save, Ctrl-z and then
    compile/run program and see if there is any problem or feature I want to add
    then go back to vim "fg". So the first run could be the only execution for
    that version of my program. 10 seconds seems like a very, very long time to
    wait for the program to run. Being a mortal, I may have even lost my train
    of thought already. Whereas even if it is a C compilation, I just need to 
    use the arrow keys for bash history (even windows console has this) for the
    compilation and execution commands which both take a split second, even
    feels instantaneous which I find really cool. It's like my computer saying -
    "Master I am here to serve you. I will drop doing anything to do your
    command." I guess I just want to be in control when I program and do not
    want to be kept waiting. 

    Another thing was it with the default Vim install, Go code formatting and
    syntax highlighting is not my favorite. C tops the list of being formatted
    by Vim nicely in plain vim installs with the least amount of tweaking.

    I know there are better ways to tweak my installation, but I just want my
    tools to run, and run fast.

================================================================================

Tue, Oct 11, 2016  9:26:11 PM

    Copy paste in Cygwin:

    ctrl  - ins      = copy
    shift - ins      = paste

================================================================================

Tue Oct  4 22:45:59 EDT 2016

    New C links for coding ncurses, sudoku (with pointers), web devel in C 
    with Moba Development:
https://www.youtube.com/watch?v=ipQPEoGztAM  - nethack
https://www.youtube.com/watch?v=9aMUyoYDI-0  - sudoku
https://www.youtube.com/watch?v=BZtSwBIaZyI  - Moba web programming in C

================================================================================

Tue Oct  4 22:43:59 EDT 2016

    Running cgi C program with fastcgi, nginx in Mac OS

    > Install fcgi
      $ sudo port install fcgi
      $ sudo port install spawn-fcgi
        
    > Install nginx 
      $ sudo port install nginx

    > create c file
        #include <stdlib.h>
        #include <fcgi_stdio.h>

        int main(int argc, char **argv) {
            while(FCGI_Accept() >= 0) {
                printf("Content-type: text/html\r\nStatus:200 OK\r\n\r\n"
                    "Hello world!");
            }
            
            return 0;
        }

    > build it:
      $ gcc -o hello hello.c -lfcgi

    > Execute fastcgi program so it is available to respond to connections
      $ spawn-fcgi -p 3000 -f /path/to/hello

    > edit nginx.conf
      $ vim /opt/local/etc/nginx/nginx.conf

        location ~ /fcgi/$ {
            fastcgi_pass 127.0.0.1:3000;
        }

    > start nginx:
      $ sudo nginx

    > check:
      $ curl http://localhost/fcgi/
================================================================================

Sat Sep  24 13:17:10 EDT 2016

    IPython and matplotlib

    In [1]: %pylab

================================================================================

Sun Aug  7 13:17:10 UTC 2016

    How to get full screen commandline in windows:

    > type cmd and "run as administrator"
    > maximize 
    > "exit" wmic
    > now type "alt-enter"

================================================================================

2016-08-07 08:24:45.1336508 -0400 EDT

   https://github.com/thewhitetulip/web-dev-golang-anti-textbook/blob/master/content/02.3.md
   
   Working on this book for "barebones" web development using go...

================================================================================

2016-07-31 10:18:19.4710111 -0400 EDT

        I have decided to create my own Unix like tools to be used in Windows. The
        current date command I am using is \work\projects\tools\datetime.go

================================================================================

        
        Uploading notes to server: 


pscp -i C:\bin\private-key.ppk *.txt theuser@22.22.22.22://home/theuser/notes/

        Copying to server:

pscp -i C:\bin\private-key.ppk theuser@22.22.22.22://home/theuser/notes/*.txt .

================================================================================

Sun Jun 26 02:17:06 UTC 2016

        Python now.

        Just to have fun. 

        Installed pygame: pip install C:\work\installers\pygame****.whl

        Testing with python:

        py.test

================================================================================

Mon Jun 13 18:53:24 UTC 2016

        Now I can do this: for Unix or unix like machines I will use vim-tmux and 
        for windows it will have to be emacs as the tooling in windows is not really
        good.

================================================================================

Wed May 25 20:37:45 EDT 2016

        I was about to stop using Emacs and go back to Vim/Tmux which is what I am
        using right now while writing this entry in my linode instance, then I just
        decided to tinker around with Ruby having seen the blog entry: 

    http://solnic.eu/2016/05/22/my-time-with-rails-is-up.html

        That blog entry made me wonder again about Ruby as Merb was mentioned and 
        how many developers got excited about using a lightweight framework for
        development. This stirred also some interest in me. What is happening in the
        Ruby dev community? What is new? What are people getting excited about. I'm
        still keeping away from Javascript. Trying to develop something fast with 
        something not Python. Maybe in Go but not yet too skilled in Go. Ruby though
        is relatively easy, I like closing scope by "end" and not just indentation,
        and I did have some experience developing in it already. Why not give it a
        try again?

        So I installed Ruby in my Win machine. Installing easy. Now what web frame-
        work? Read some documentation. Only Sinatra won. Done. 
        
        gem install sinatra

        Then when I tried coding the source in vim, indentation was funky....
        Tried Emacs in evil-mode. Indentation good. Font good. Finding files -
        better than Vim. Emacs-evil-mode wins!

================================================================================

Sat May 14 08:23:09 EDT 2016

    Kill a process running on a port (example 1024):

    $ fuser 1024/tcp
    1184
 
    $ kill 1184
    

================================================================================

Sat May 14 06:50:09 EDT 2016

    This post inspired me to install go, pathogen and faithvim on my linode:

    http://yieldthought.com/post/31857050698/ipad-linode-1-year-later

    Installed pathogen
  
    $ mkdir -p ~/.vim/autoload ~/.vim/bundle && \
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
    
    $ sudo vim /etc/vim/vimrc:

execute pathogen#infect()
syntax on
filetype plugin indent on
" Source a global configuration file if available
if filereadable("/etc/vim/vimrc.local")
  source /etc/vim/vimrc.local
endif

    Install vim-go
        
    $ mkdir ~/.vim/bundle

    $ git clone https://github.com/fatih/vim-go.git ~/.vim/bundle/vim-go

    
================================================================================

Fri May 6 06:56:09 EDT 2016

    Just installed Netbeans and JRE on my Windows computer. Trying to get a feel
    of "continuous delivery" using Gradle. BTW, with the new internet speed
    at home. 167 MB took less than a minute to download. Sweet!

    Just downloaded Netbeans with the JDK. Trying it out - inspired by this
    article I found from ycombinator:

    http://www.nicolasbize.com/blog/30-years-later-qbasic-is-still-the-best/

    Anyway, whatever language, if it works, it is a go for me.

================================================================================

Thu Apr 28 22:17:09 EDT 2016

    Got GOPATH set in Windows go. Had to use "GIT cmd" as shell as I only have
    git runnable from that console. Set my GOPATH to:

    GOPATH
    C:/Users/user/projects/my_go

================================================================================

Thu Apr 28 06:56:54 EDT 2016

    Downloading mongo for windows... Maybe I can pull this off....
    Took about 30 seconds on my new internet connection.
    We'll see how that goes later... Got distracted with router setup

================================================================================


Thu Apr 28 06:43:49 EDT 2016

    TWITTER_VOTES PART 3

    So I downloaded nsq binaries from http://nsq.io/deployment/installing.html
    unpacked and went to directory then
    $ sudo cp * /usr/local/bin

    Now these two both work!

    $  nsqlookupd

    $ nsqd --lookupd-tcp-address=localhost:4160

    My mongo is still not working. I plan to use either redis or sqlite for this
    one. This seems like minor, but may be a major fix for me....

================================================================================

Tue Apr 26 23:36:49 EDT 2016

    TWITTER_VOTES PART 2

    $ nsqlookupd  #does not work

    $ nsqd --lookupd-tcp-address=localhost:4160 # does not work


================================================================================

Tue Apr 26 23:16:16 EDT 2016

    TWITTER_VOTES PART 1

    Trying the Twittervotes app in Go Programming Blueprints:

    $ brew install nsq

    $ sudo chown -R $(whoami) /usr/local

    $ sudo chown -R $(whoami) /Library/Caches/HomeBrew

    $ brew doctor

    $ brew link nsq

    $ nsqlookupd

    Now let's get the go driver for nsq:

    $ go get github.com/bitly/go-nsq

    Now my problem is MongoDB does not install in my old macbook. I will just
    use sqlite or redis - whichever is easier to get up and running.

    Start nsqlookupd
    Start nsqd
    Start whatever datastore... (continued on next post)

================================================================================

Tue Apr 26 20:37:46 EDT 2016

    Rust tutorial:
    http://rustbyexample.com/hello.html

================================================================================

Tue Apr 26 20:26:49 EDT 2016

    Installing rust-mode in emacs.

    M-x package-list-packages

    Scroll down to rust-mode then type "i" to mark it for install

    Type "x" to start install packages.

================================================================================

Tue Apr 26 04:13:51 EDT 2016

    Being a programmer after 40:

https://medium.com/@akosma/being-a-developer-after-40-3c5dd112210c#.72sk6ew7a

================================================================================

Wed Apr 20 18:40:19 EDT 2016

    Using 4 spaces for tabwidth in emacs:

    (add-hook 'go-mode-hook
      (lambda ()
        (setq-default)
        (setq tab-width 4)
        (setq standard-indent 4)
        (setq indent-tabs-mode nil)))

================================================================================

Sun Apr 17 20:45:48 EDT 2016

    This is were my .emacs file is on Windows:

    c:\Users\the_user\AppData\Roaming

    M-x package-install   -> go-mode

    Now opening a .go file syntax hightlights go source, then using
    M-x evil-mode is even better.

================================================================================

Sun Apr 17 02:25:42 EDT 2016

    Kali Linux up and running on flash drive. Configuring Emacs first and try 
    evil-mode.

================================================================================

Mon Apr 11 20:35:41 EDT 2016

    Currently listening to Batman on Spotify.

    I had the python script for turning schedule.xls to caseloads.txt.

    Now get the paysources....

================================================================================

Mon Apr 11 20:34:21 EDT 2016

    Reconfigured data and time in my raspberry pi with:

    $ sudo dpkg-reconfigure tzdata

    This brings you to a couple of menus that lets you specify your timezone.

================================================================================

Mon Apr 11 6:53:20 EDT 2016

    Freeing space in raspberry....

    # du -sh *   

    Doing this from root into /usr/share/doc showed that share used about 800 M
    of space.

    # apt-get --purge remove text.\*doc$ 

    Removed about 800 M of doc files is share...

================================================================================

Mon Apr 11 01:05:47 EDT 2016

    I do agree that emacs is a very good programming environment with lots of 
    stuff to make programming productive, but... I am just in a hurry to finish
    the Python script I needed to parse files. The old program used a database
    and I decided that this time, I would go with as little "dependencies". And
    the script just reads an excel file and then prints it out with data sorted
    out. It was a pain trying to think of the code, the problem in the
    algorithm and the use of a new text editor. 

    I just wanted to give emacs a try as I am programming in Windows to be able
    to extract the data from a windows program.

    Even moving text, even typing speed was affected. At this time, I am in a
    crunch. Can think faster with the current setup. Can code faster with the 
    current setup. Familiarity of the coding environment and language. 

    I still plan to study emacs and its code though, including lisp.

    At this time, vim and python - I am fastest this way.

================================================================================

Sun Apr 10 15:00:49 UTC 2016

    Pasting the date from emacs not yet too easy:
 
    C-u M-! date (puts shell command "date" into buffer)

================================================================================

Sat Apr  9 11:20:45 UTC 2016

    Diving into Emacs. Writing this post currently in Emacs. Got the tutorial
    from here:

    http://blog.aaronbieber.com/2015/05/24/from-vim-to-emacs-in-fourteen-days.html

================================================================================
Thu Apr  7 12:29:16 EDT 2016

    And one more thing: Turn of internet at times. Limit surfing..

================================================================================

Thu Apr  7 11:41:49 EDT 2016

    Physical/Mental preparation for coding:
    > enough sleep
    > enough exercise
    > managing notes from work
    > writing notes on journal, tech notes and on moleskin notebook
    > using calendar as a personal secretary so no appointments get forgotten.
      Who to call, appointments, what notes to write, etc.
    > spending more time with family - Saturdays are homecare light work and
      Sundays are not work and catch up on notes.
    > Going to gym with Janjan

================================================================================

Thu Apr  7 11:35:39 EDT 2016

    USE LESS CODE MORE (using less libraries, tools and frameworks work)

    It saves time and energy learning a new framework.
    It saves time, energy and motivation to not get into bugs and configuration
    hell from using unfamiliar or unstable libraries, frameworks.
    Not using ORM to cut down on studying the ORM or configuration and then I
    end up just testing the basic functionality of the models (CRUD).
    Now I just code the functionality I need directly. I do not have the time to
    be a framework expert.

    USE MORE ONLY WHEN IT HELPS.

    Example is I use an python library for reading excel files with a very easy
    api. Not too powerful but understandable.


================================================================================

Thu Apr  7 11:27:43 EDT 2016

    How I code:
    > Thinkpad with good battery life, keyboard and music
    > Metal music (Metallica and stuff)
    > Vim, Python, git (for notes and journal) - see last entry for setup
    > TV on with something not too interesting (Action series).
    > Sit and stand.
    > Workout.
    > "Easy" testing. Combination of py.test and just manually checking program
      output. Testing is not formalized.
    > Used python as I am familiar (get around my head), setup was easy, 
      libraries - did not have to read up much to code. Fairly powerful, not too
      low level that you have to code everything yourself and did not have the
      "configuration hell" with some languages. Readily available in Unix like
      and windows easily.

    This setup works. Last night I was able to code the script that will compare
    two files and print out what entries have not yet been done based on the 
    older (marked) file. Saves me time and a lot of brain cycles at work.

    Coded in one night! I cannot dispute that.

================================================================================

Thu Apr  7 11:18:13 EDT 2016

    My new workflow/setup.

    Using my Lenovo Thinkpad 450s exclusively. Using my Macbook as a backup and
    unix based programming environment. I just turn the Mac on and connect to it
    via ssh. Using Putty and adjusted screen fonts to Lucida Console 14 pt - way
    better to have large fonts. My raspberry pi is always on and I connect to it
    for backup and maybe work on C programming. Currently programming in Python
    in my Thinkpad. Downloading Microsoft Visual Studio for C programming. I
    found a tip in "Handmade Hero" video for setting up and console based 
    environment for C/C++ development.

    Music       : Metal, definitely for programming.
    Text editor : vim/gvim with larger fonts and dark backround.
    Browser     : Firefox
    Console     : cmd with larger fonts
    Python      : using py.test (painless testing)
    programming : "data driven" - just basically testing code against real data
                  and making sure that output is correct. That simple.

================================================================================

Thu Apr  7 11:08:25 EDT 2016

    Coding in Python. Coded last night after dinner. Had Netflix on with 
    "American Odyssey" on. Also had Metal music running in Spotify. Coded using
    my Lenovo T450s. 

    Why it makes sense to code in a Thinkpad 450s.
    > Best keyboard!
    > Rugged laptop. I am not afraid that I would break anything when I carry
      this computer in my bag. 
    > Trackpoint. I never knew that using this feature would really make working
      in situations with muliple windows, copy paste from gui for data sources,
      basically replacing the mouse without moving my hands too far from the
      keyboard.
    > Battery life! (5 hours at least, just received my 6 cell battery which has
      even more juice
    > Weight - something I can really put in my lap.
    > Size. 14 inch monitor good enough (not small, not big), to be productive 
      and mobile. Thin - easy to carry around.
    > Windows makes me get Windows programs running (this is where I get my data
      from which I can crunch. Although I love OSX, BSD and Linux, I need to 
      gather my data from Windows based applications so this works.
    > Blackbox look. Looks like computers I use at work, so I can bring this and
      use it at work and for coding.


    I made the right choice.
   

================================================================================

Wed Mar 23 22:39:54 EDT 2016

    Using ssh-agent and ssh-add to use ssh without entering passphrase:

        eval `ssh-agent -s`
        ssh-add

================================================================================

Wed Mar 23 07:54:58 EDT 2016

    Goal is: make simple apps that do simple things.

================================================================================

Wed Mar 23 07:07:47 EDT 2016

    I am off work today, just one homecare patient at 9 AM. 

    Working on adc project. Writing SQL by hand and coding in C. I think this
    is what I like better. Leverage what I learned more than ten years ago. 
    Using the newer tech and deeper understanding. SQL and C still rock today.
    I used SQL with either Java, PHP or Rails back then. Mapped out CMS data-
    bases in a big whiteboard until about 2 am and inserted my own tables and
    tweaked the CMS to do our work. That was a real hack. Makes me feel excited
    just thinking about it.

    Got to do it.

================================================================================

Wed Mar 23 06:43:49 EDT 2016

    Monday and Wednesday I was not able to do much of coding or workouts, 
    although I was able to play a little tennis with Janjan in the Kinderhook
    tennis area last yesterday, Tuesday. Caught up with work in Barnwell and 
    also with my homecare. I think it is a good idea to devote Sunday PM, Mon-
    day AM until Tuesday to play catch up and get ahead. Then the rest of the
    week would be doable. Get ahead of the game. So I have not been getting too
    much sleep Sunday nights and get to sleep better on Monday. I think this
    makes sense for me as for so many years in College, I had to travel from
    Bohol to Cebu (4 hour boat trip) on Sunday night and then sometimes even
    had to miss some of Monday... That was not a good idea and it was so lone-
    ly. 
    But doing it this way:
    > Get all loose ends done and get ahead of work Sunday PM and Monday am,
      power through Monday 
    
    I use my energy and still be with family. And it is getting ahead, not 
    being behind. I also am able to just make it through Monday as it is mostly
    dreary anyway. No more Sunday night boat trip which was one of the least
    pleasant memories of my College and Cebu working days. 


    Sunday - Family and most workout then catchup on all notes.
    Monday - least workouts and get ahead of work.

================================================================================

Sun Mar 20 19:09:01 EDT 2016

    Sunday 6 PM and up seems to be "my time". I feel that I can tackle stuff
    like coding, reading, working out and even writing notes for my homecare PT
    stuff. I seem to be "available" at this time. It is also good or everyone to
    be home at this time so they can tackle the coming week's challenges. I like
    to "frontload" my work - I even used to go very early to work on Monday 
    6:30 AM to do scheduling or even do it Sunday nights at my daytime PT work.
    Yes, Sunday night or Monday early mornings were spent there. For about 2
    years of my life.  (Continued at my journal page....). Anyway, if I could do
    it for work, I could do it for myself....

    Sunday just a little bit after 7 PM. Church at 10:30 AM done. Cooked for 
    family lunch done. Time with family and a couple of friends and then had a
    little nap. Decided to get some coffee a while ago, although I have decided
    to cut on coffee and alcohol for most of the week. Sundays are always the 
    exception. Now the plan:
    * Read
    * Workout
    * Code
    * Write on journal
    * Write PT notes

    Mind is relatively clear. And a little while before this, just did a ritual:
    cleaned coffee pot and water dispenser - took about 10 minutes. That was my
    meditation. Also put all my Homecare scheduled visits in my Google calendar.
    Also some plans for this week. Now I feel that I have planned. Nowadays too
    I finish all my dayjob notes on time since I do not have the scheduling duty
    already. Now just the MDS to be on time. I need to write that tool to merge
    MDS lists and mark what are done and not done (will save me about 30 minutes
    every day and that will be my morning time which is very important for me).


================================================================================

Sat Mar 19 09:26:32 EDT 2016

    Trying to get into coding mindset in 5 minutes.

    .. 4 minutes done. Firing up Pandora

    .. 6 minutes.. Spotify house on


================================================================================

Thu Mar 17 21:23:58 EDT 2016

    Database labs (execution is everything) - shows that we can maybe just share
    the code and then be able to market something somehow. Hmmm, sqlite comes
    into mind. One great codebase, very much used by a lot of people.

    www.kalzumeus.com - running a software business on 5 hours a week... Or 
    coding 3 hours a day, everyday no exceptions, forever. Or in my case, coding
    30 minutes a day...

    Time debt. Make tools to save time... That kind of stuff.
   

================================================================================

Tue Mar 15 06:50:58 EDT 2016

    One more reason for Mac: HAPPINESS...

================================================================================

Tue Mar 15 06:49:00 EDT 2016

    I am sold: totally going to shop for a Macbook air soon.

FROM freethink.txt:

Time to code:
  Best would be early in the morning.

Best machine for coding.
  (mac)

What can I say? Typing in my Macbook is
  FREAKING AWESOME!!
  I would not have any other machine at
    this point to type on...
  Nor do I have one comparable...

Why is the Macbook awesome:
  Still has some battery. (2-3 hours)
  Keyboard rocks
  Very good "sleep" functionality.
  Just works.

================================================================================

Tue Mar 15 06:22:03 EDT 2016
(Taken from my journal entry)

    As I thought, I can program most productively in my Macbook. Planning to buy
    either a Macbook 11" or an HP Elitebook 12". Elitebook has bigger memory and
    costs about $300, Macbook Air a minimum of $460. Elitebook 12", Macbook Air
    11". Macbook has good keyboard, Elitebook might have good keyboard.
    Macbook has OSX, Elitebook has Windows (I would have to install linux). 
    Macbook should have good battery life, Elitebook about 3 hours. Macbook has
    good sleep function, Elitebook depends on linux. Macbook will be easy to 
    connect to network and has good PDF readers. Elitebook...

    Macbook Air 11", wins even with price. I better buy a good almost like new
    or new one (OLD version or newest).

    Macbook Air 11" wins!

    John Carmack when Id was in full scale development and when they just 
    started having money, once went out on a cold day, drove his car to for a
    bit and came back with a Next Cube. It was his investment. Back then the
    Next Cube cost about $10,000. That was about 20 years ago. John Carmack
    coded the game Wolfenstein and Tim Berners Lee used a Next Computer to 
    "build" the internet. Cool STUFF! Macbook Air wins in my game.
    
    Now to look for stickers for my Mac.

================================================================================

Sat Feb 27 09:43:27 EST 2016

http://ewanvalentine.io/why-go-solves-so-many-problems-for-web-developers/

================================================================================

Tue Feb 23 21:47:47 EST 2016

http://metal.mit.edu/brief-history-metal:

Metal notes, chronological:
> Black Sabbath (started it, workman like)
> Deep Purple   (faster virtouosity)
> Judas Priest, Hellbent or Leather
> Iron Maiden , Run to the Hills
  Motorhead, Iron Fish
> Metallica

================================================================================

Sun Feb 21 09:25:19 EST 2016
    
    Using zeromq security:

    http://hintjens.com/blog:49

    The scalable C language:

    https://hintjens.gitbooks.io/scalable-c/content/chapter3.html
    

================================================================================

Sun Feb 14 09:20:55 EST 2016

    Python's killer apps for blogging:

    http://tech.marksblogg.com/website-cdn-with-pelican-and-s3cmd.html

================================================================================

Thu Feb 11 18:45:19 EST 2016

    Using text files...
    http://lifehacker.com/ten-clever-uses-for-plain-text-files-that-can-increase-1662774267

================================================================================

Thu Feb 11 06:58:34 EST 2016

    This is a nice little source of tips about small things someone learned
    across a variety of languages and tech while working at Hashrocket:

    https://github.com/jbranchaud/til

    Then how to code go to convert "curl" commands to go:

    https://mholt.github.io/curl-to-go/

================================================================================

Tue Feb  9 21:35:15 EST 2016

    The tools, the language and the workflow.

    I think that when programming, it is not only the language itself that makes
    it fun and productive but also the tools available and the workflow... I 
    like tools that are simple and that I know how to use. I do not like to 
    install a library/plugin and then later on it does not run (like the
    nightmare I had with Ruby gems and versions). I did not know why there had
    to be so many dependencies and then later on they were broken.

    Anyway, the workflow. I will describe mine for this short snippet that did 
    not work (after I added the scaffolding code):

        #include <time.h> 
        char *now; 
        char *date; 
        /* original snippet starts here */
        time(&now);
        strcpy(date, ctime(&now));
        date[strlen(date)-1] = '\0';
        /* original snippet ends here */

    So the workflow:
    1. save file after editing (using vim ":w")
    2. Ctrl-z to get out of vim temporarily
    3. gcc -Wall the_art.c -o the_art
    4. ./the_art (runs the program)
    5. fg
    6. back to 1

    Steps 3 and 4 I do not have to type, just use the "up" arrow for command
    history.

    It had bugs so did not compile yet. Fixed bugs. I ran then had segmentation
    fault. I decided to use Valgrind to be safe. Oh, my Mac does not have 
    valgrind. Easy, I have a raspberry pi always on with gcc, valgrind, python
    and some other good stuff (like vi with tags to C library code).

    scp *.c pi@192.168.0.xx://home/pi/projects/c_snippets

    Used steps 1 - 6 but changed 3 and 4 to use valgrind as follows:

    3. gcc -Wall -g the_art.c -o the_art
    4. valgrind ./the_art

    Kept doing the same routine, until I found a solution.
    It takes just a couple of seconds to save(":w"), get out of vim("Ctrl-z")
    and compile (2-3 up arrows). 

    
================================================================================

Tue Feb  9 21:26:52 EST 2016

    Learning again that C is unreasonably good. Stable, simple, fast, uncompro-
    mising. This guy thinks so too:

    http://damienkatz.net/2013/01/the_unreasonable_effectiveness_of_c.html

    I currently reading "The Practice of Programming" by Kernigan and Pike, and
    find that their are a few bits of of essential tips for programmers and 
    especially for C programmers. Going through some code about commenting your
    code, I found a snippet that resulted in a segmentation fault. It compiled
    but the segmentation fault happened when I ran the code (more aoubt this 
    later). But I was able to hack a bit and experimented. Used Valgrind and
    hacking away and read a little bit of the man pages and whalla! It ran...

================================================================================

Sun Feb  7 13:09:12 EST 2016

    Found a way to read whole file in C in a better way using dynamic alloc-
    ation here:

    /Users/baloi/projects/c_snippets
    (Now implemented in ~/projects/c_snippets/file_open.c 

    Currently also reading:
    "The Practice of Programming" by Brian Kernigan and Rob Pike
    "The Art of Unix Programming" by Eric Raymond

    TPOP has good idioms for C and other languages and a very good regex matcher
    in a few lines of C.

    TAOUP has some stuff about the Unix approach, good program design, etc.

    Not even a third of the way through both books and already it is giving me
    much info, enlightenment...

================================================================================

Sat Feb  6 15:28:12 EST 2016
    
    C programming, improving, see Leif Walsh's answer:

    https://www.quora.com/What-is-the-right-way-to-improve-my-practical-programming-in-c

    Definitely someone to follow, coding-wise. A C programmer by trade...
    
    Code reading Spinellis:

    http://www.spinellis.gr/codereading/spinellisch02.pdf

================================================================================

Thu Feb  4 19:38:56 EST 2016
    This might just be what I am looking for...

    Maru is a desktop OS on an Android phone. Switch between phone and Desktop.
    Connect phone to HDMI and connect Bluetooth keyboard.

    http://maruos.com/#/

    And as a side note, 20 things nice to have:

    http://www.amazon.com/b/ref=sl_gw_topshov_twenty/ref=br_isw_strs-3?_encoding=UTF8&ie=UTF8&node=13630385011&pf_rd_m=ATVPDKIKX0DER&pf_rd_s=desktop-top&pf_rd_r=02TKBP82ME8RMHSJJFY3&pf_rd_t=36701&pf_rd_p=2402280002&pf_rd_i=desktop

================================================================================

Thu Feb  4 06:46:06 EST 2016

    fread in C when reading binary files in unix is different when using it in
    Windows. I opened the file using:


        conn->file = fopen(filename, "r+");

    This link 
    (http://stackoverflow.com/questions/11717120/unexpected-return-value-from-fread)
    suggests that fopen be used with "rb" flag

        conn->file = fopen(filename, "rb+");

    I will give it a try later, but I am also thinking about using mingw on
    windows. I just tried TCC last night.

    My little side project is a database that uses structs and write the structs
    (and read them) in binary format.

    Or I may have to read and write to text files instead, as this may work for
    my other little project which will parse MDS lists and determine which were
    done and not done - this tool I need badly.

================================================================================

Sun Jan 31 22:47:56 EST 2016

    This weekend, I was not able to code my planned dayprog planner database,
    but I had fun with pcap capture library.

    Had pcap installed and running on my raspberry pi by Saturday morning. Had
    it running in OSX later on. Followed the tutorial in: 
    http://www.tcpdump.org/pcap.html

    Took it slow. Bit by bit. First compiled with #include <pcap.h>. Then 
    slowly added functionality. Had visitors saturday afternoon to night so I
    had a coding stop for a bit but coded again a little more Saturday night.

    Saturday morning more done, afternoon for 2 hours and then finished the
    whole thing at 10:30 PM tonight after my run.

    Got it done!

    From now on, a tutorial should be done in due time. I will not hurry at all
    as I will not learn much that way. It was about a 300 + line program with
    lots of comments for the functions used. Coded in C. Followed the tutorial,
    but I think I still have to revisit this and code more my own.

    It had a callback function which called printing functions in hex and ascii.
    
    Totally rocks!

================================================================================

Sun Jan 31 22:35:49 EST 2016

    Packet capture code using libpcap is working. Nice! Learning more C idioms.
    The little sniffer program was written in good style. Uses pointer offset
    locations. 
    
    Has callback function. Cool!

    Code is in ~/projects/packet/sniff.c

    The function:
    
    int pcap_loop(pcap_t *p, int cnt, pcap_handler callback, u_char *user)

    this is the key to the callback mechanism. So each time a packet is read,
    the callback function "callback" is called with arguments.

================================================================================

Sun Jan 31 15:00:38 EST 2016

    Studying code by typing it in and modifying (one way to learn, a good one).

    I have been coding the sniffer in C for a couple of hours now. About 250
    lines with comments explaining some parts of the program. So it could be
    about 200 lines. I had also some code in there from past pcap library use
    practice snippets. So it could be close to 150 lines of code. 

    Now, this is just trying to copy and get to understand the sniffer code in
    C. 

    Method:
    1. copy a small part of the code (about 1 to 5 lines only)
    2. compile/run
    3. understand the code

    4. edit code if needed to fit my liking

    This will be my defacto standard of studying C code from now on...

================================================================================

Sun Jan 31 10:22:24 EST 2016
    I have to read some of these books:

    https://sivers.org/book

================================================================================

Sat Jan 30 11:46:44 EST 2016

    Installing pcap from tcpdump site for packet stuff:

    > Downloaded pcap:
    $ http://www.tcpdump.org/release/libpcap-1.7.4.tar.gz

    > Unpack
    $ tar -zxvf libpcap-1.7.4.tar.gz

    > apt-get update
    $ sudo apt-get update

    > install flex
    $ sudo apt-get install flex

    > install yacc through bison
    $ sudo apt-get install bison

    > configure, make, make install
    $ ./configure

    $ make

    $ sudo make install


================================================================================

Fri Jan 29 06:47:35 EST 2016

    Gopher academy has a few bit of short projects to tinker with like, a go &
    JSON database, parser and lexer. It seems one way to start... I have done
    worse in the past so why not?

    https://blog.gopheracademy.com/


================================================================================

Fri Jan 29 06:39:50 EST 2016

    Having more time, less money. The upside to more time though is you have
    time to be more observant. Think more. Live more. Code more. Write more.

================================================================================

Fri Jan 29 06:03:36 EST 2016

    Taken from my journal with the above date and time:

    I should be writing more on my journal. I have been writing a bit on my BSD
    notes though. I think is it good to look at my git logs to know home much
    I have been "working". Right now, notes and some projects have been tracked,
    but my "projects folder has not been....". Maybe I should log all the 
    "creative" work I have done and the "freewriting" too. Hmm. just a thought.

    Anyway, looking into doing "go" or "c". Learning to have a rudimentary 
    database in C. Porting to go or not? Go has encryption, go routines, and
    networking with it. I have also found a bare tcp server an client sample.
    Trying to figure out patterns for file access. Maybe I should look into
    the simple go database implementation with JSON serialization sample and
    then just change it to the c-style implementation ..... Hmmm. Time to look
    into some code.

    I am trying out small project samples from other people. Might try to read
    on medium sized samples later on... But I feel I still have the need to 
    be grounded on the small snippets of code which I do enjoy doing. I shall
    do this and maybe bigger projects later on. 0MQ was good for a while then
    things got complex. I'll go back to 0mq and nanomsg later on when I need
    a networking stack for my database maybe. Maybe that is....


================================================================================

Wed Jan 27 06:47:22 EST 2016

    Connecting programs together with sound?
    http://joearms.github.io/2016/01/28/A-Badass-Way-To-Connect-Programs-Together.html

    This is from the speaker of this video, which is also cool (the mess we are
    in):
    https://www.youtube.com/watch?v=lKXe3HUG2l4
================================================================================

Sat Jan 23 07:25:55 EST 2016

    Using valgrind:
    
    Compile your program with the -g option:

    $ gcc -Wall -g your_program.c -o your_program

    Then let it run with valgrind:

    $ valgrind --track-origins=yes ./your_program

================================================================================

Thu Jan 21 22:07:33 EST 2016
    
    $ ./configure
    $ make
    $ make check
    $ sudo make install
    $ sudo ldconfig

    Trying nanomsg...

    Swap #include <libc.h> with:

    #include <unistd.h>
    #include <string.h>
    #include <pthread.h>

    And compiling nanomsg programe like nano_pipe.c for example:

    $ gcc nano_pipe.c /usr/local/lib/libnanomsg.a -o nano_pipe
   
    But that was static linking. better dynamic:

    $ gcc nano_pipe.c -L/usr/local/lib/ -lnanomsg -o nano_pipe 
    

================================================================================

Mon Jan 18 22:59:07 EST 2016

    Scalable C: https://hintjens.gitbooks.io/scalable-c/content/chapter2.html

    This looks like a very promising piece of work. Includes C style and
    good programming practices....

================================================================================

Sun Jan 17 14:03:03 EST 2016

    ZeroMQ is really pulling me into programming programs that I find really
    cool. Messaging across machines, client and server, publish and subscribe.
    These are what I like. Coded in C. Even the ZeroMQ style of coding really
    makes sense. Instead of using function pointers and structs to have some-
    thing like classlike behaviour, 0mq just uses naming conventions and passes
    pointers to structs, like:

    void *context = zmq_ctx_new();
    void *requester = zmq_socket(context, ZMQ_REQ);
    // here's a sample:
    zmq_connect(requester, "tcp://localhost:5555");
    // another:
    char buffer[10];
    zmq_send(requester, "Hello", 5, 0);
    zmq_recv(requester, buffer, 10, 0);
    zmq_close(requester);
    zmq_ctx_destroy(context);
    
    How cool is that!

    After unsuccessfully trying to install zeromq and having a lot of libsodium
    library not found problems when building zeromq, I almost gave up on it, 
    until I just did:

    $ brew install zeromq

    ==> Downloading http://download.zeromq.org/zeromq-4.1.2.tar.gz
    ######################################################################## 100.0%
    ==> ./configure --prefix=/usr/local/Cellar/zeromq/4.1.2 --without-libsodium
    ==> make
    ==> make install
    /usr/local/Cellar/zeromq/4.1.2: 63 files, 3.3M, built in 107 seconds

    Found it from here: 
    http://cbcg.net/blog/2011/07/30/getting-zeromq-and-jzmq-running-on-mac-os-x/

    Cloned my distributed applications testbed into ~/projects/distributed and
    compiled like this:

    $ gcc hello_client.c -L/usr/local/Cellar/zeromq/4.1.2/lib/ -lzmq -o hello_client

    $ ls /usr/local/Cellar/zeromq/4.1.2/lib/

    libzmq.5.dylib
    libzmq.a
    libzmq.dylib
    pkgconfig

    I guess -L prefix points to the "lib/" folder which contains libzmq.a
    which is used by the -l prefix of gcc.

    Rock on...
================================================================================

Sun Jan 17 10:01:29 EST 2016

    Coded before breakfast and a little bit more after breakfast trying out
    zero mq. This is the sort of programming I like! Sockets, client-server,
    publish - subscribe. Makes the blood go uhm.

    weather_updater.c is a program that just publishes mock weather data. I 
    tried modifying py_hags/tcp_client.py to listen to port 5556 where it 
    publishes, but got "garbled" data. Telnet sort of does the same thing:

    $ telnet 192.168.0.11 5556 > response.txt

    Tweaked distributed/src/weather_client.c to print out every single 
    weather data sent as it is received.

    All working on my raspberry pi.

    Uploaded to git.

================================================================================

Sun Jan 17 07:28:21 EST 2016

    Hello 0mq !

    Built libsodium and zero mq:

    (https://hintjens.gitbooks.io/scalable-c/content/chapter1.html)

    cd $HOME/projects

    # Install libsodium
    git clone https://github.com/jedisct1/libsodium
    cd libsodium
    ./autogen.sh && ./configure && make -j 4
    make install
    cd ..

    # Install libzmq
    git clone https://github.com/zeromq/libzmq
    cd libzmq
    ./autogen.sh && ./configure && make -j 4
    make install
    cd ..

    # Build CZMQ again...
    cd czmq
    ./configure && make -j 4
    make install
    cd ..

    Compiled my first zero mq program:

    $ gcc -Wall hello.c -o hello -L/usr/local/lib -lzmq 

    $ ./hello

    hello: error while loading shared libraries: libzmq.so.5: 
    cannot open shared object file: No such file or directory

    Found a solution here: 

    http://stackoverflow.com/questions/17275875/zmq-libzmq-so-3-cannot-open-shared-object-file-no-such-file-or-directory

    $ sudo ldconfig

    This will update the system library cache. I had already successfully built
    libzmq and libsodium.

    It took a couple of hours for the total compile/make times, but it is worth
    it to have zero mq installed in my raspberry pi! On my Mac it has not
    successfully been built though due to libzmq build cannot find libsodium...
    Maybe another time in Mac. Pi for now!

================================================================================

Sat Jan 16 16:20:53 EST 2016

    Scalable C - Writing large-scale Distributed C

    https://hintjens.gitbooks.io/scalable-c/content/index.html

================================================================================

Tue Jan 12 20:56:03 EST 2016
    Listening to Hacking The Overmind Radio in Pandora...

    Uses of netcat "nc", a very powerful tool indeed:

    http://www.catonmat.net/blog/unix-utilities-netcat/

    ---------------------------------------------------

    Setting bash to 'vi' mode: (http://www.catonmat.net/blog/bash-vi-editing-mode-cheat-sheet/)

    $ set -o vi

    To get back to emacs mode:

    $ set -o emacs

================================================================================

Sat Jan  9 17:23:28 EST 2016

    Learning hard stuff

    https://medium.com/learning-new-stuff/a-simple-technique-to-learn-hard-stuff-ffaa7879bf7c#.hmo5lybld

    1. Use it before you know it. Maybe a video tutorial

       a. Build from day one
       b. Gives you sample code
       c. Discover your unknown unknowns

    2. Address your struggles

    3. Build stuff

================================================================================

Wed Jan  6 22:53:47 EST 2016
    Taken from  
    Compiling SDL with gcc on Mac (c code):
    
    get the linking flags:

    $ sdl-config --cflags --libs

    Which outputs:
    -I/opt/local/include/SDL -D_GNU_SOURCE=1 -D_THREAD_SAFE -L/opt/local/lib 
    -lSDLmain -lSDL -Wl,-framework,Cocoa 

    So do this to compile:

    $ gcc -Wall -c main.c -o main.o
    $ gcc -I/opt/local/include/SDL -D_GNU_SOURCE=1 -D_THREAD_SAFE 
      -L/opt/local/lib -lSDLmain -lSDL -Wl,-framework,Cocoa  main.o -o c_only

    
    Answer was found in:

    http://stackoverflow.com/questions/4019892/compiling-sdl-on-a-mac

    Raycasting example taken from:

    https://www.youtube.com/watch?v=HQYsFshbkYw
    http://bisqwit.iki.fi/jutut/kuvat/programming_examples/portalrendering.html

    Now works!!!

================================================================================

Tue Dec 29 21:00:34 EST 2015
    
    Inspirational technical books that are not technical

    http://blog.fogus.me/2015/07/07/inspirational-technical-books-that-are-not-technical/

================================================================================

Mon Dec 28 20:14:12 EST 2015

    Codewalk: Share Memory By Communicating

    https://golang.org/doc/codewalk/sharemem/

================================================================================

Fri Dec 25 07:30:05 EST 2015

    Handmade quake:

    http://philipbuuck.com/announcing-handmade-quake

    Modding doom:

    http://eev.ee/blog/2015/12/19/you-should-make-a-doom-level-part-1/

================================================================================

Thu Dec 24 22:46:56 EST 2015

    Detecting wireless cameras:

    https://julianoliver.com/output/log_2015-12-18_14-39

================================================================================

Sat Dec 19 08:31:25 EST 2015

    flow based programming:

    https://groups.google.com/forum/#!msg/flow-based-programming/iaKhbABJ9fw/XlrMf-dnBgAJ

================================================================================

Sun Dec 13 08:24:28 EST 2015

    "Maximizing" a tmux pane:

    > Ctrl-B z

================================================================================

Thu Dec 10 19:39:06 EST 2015

    Vim plugins to try:

    http://adamdelong.com/5-vim-plugins-helped-switch-sublime/

================================================================================

Wed Dec  9 22:33:37 EST 2015

    Try using these Python libraries:

    "dateutil" and "requests"

================================================================================

Wed Dec  9 22:06:54 EST 2015

    Creating Raspberry pi with Kali linux for pentest

    http://lifehacker.com/how-to-build-a-portable-hacking-station-with-a-raspberr-1739297918

    Bobby tables for preventing SQL injection:

    http://bobby-tables.com/

================================================================================

Sat Nov 21 09:01:52 EST 2015
    
        This is a talk from Golang conference UK about security which I should
        still review:

            https://www.youtube.com/watch?v=ViBRx-F4Z2U&list=PLDWZ5uzn69ezRJYeWxYNRMYebvf8DerHd

        This is linked from a link from: 

            https://blog.golang.org/

        The blog itself is a very good and is good morning material.

        Anyway, the security talk. The resource person, Eleanor McHugh has a
        book, "A Go Developer's Notebook" which is a great 
        study-by-hacking-snippets-of-code and putting in in my 
        ~/my_go/src/snippets, running, modifying and readig the thankfully short
        but very enlightening explanations from a hacker's collection of code
        snippets used in her talks through the years. The book can be bought
        from $6.00 to $24.00 at https://leanpub.com/GoNotebook. Great!

================================================================================

Wed Nov 18 06:58:26 EST 2015

    Try this out in go:

    http://libmill.org/tutorial.html

    This seems like a good equivalent in go:

    http://loige.co/simple-echo-server-written-in-go-dockerized/

    Tested this go app with netcat and echo:

    $ echo "Hello server" | nc localhost 3333  


================================================================================

Wed Nov 11 21:52:20 EST 2015

    Just playing with dc application right now. Using structs in go. Seems ok.

================================================================================

Sun Nov  8 21:59:15 EST 2015

    To make install go packages:

    $ go get github.com/gopackage

    But we have to set $GOPATH in .profile (for raspberry pi)

    GOPATH=$HOME/my_go

    my_go would have src/, bin/ and pkg/

================================================================================

Sun Nov  8 20:41:07 EST 2015
 
    Using nmap to find ssh ports:

    $ nmap -p 22 --open -sV 192.168.0.0/24

    -p      = port (in this case 22)
    --open  = suppress output for clients that are not listening
    -sV     = display the versio string reported by the scanned server
    192.168.0.0/24  = target network (/24 specifies a subnet of
                      255.255.255.0

================================================================================

Sat Nov  7 06:58:04 EST 2015

    Update to GO in raspberry pi. Running as per installation instructions
    below! I just needed to make "sudo apt-get update" work. Then installed
    vim. Then set go/bin to be in the path. Sweet.

    Using tar and scp to get some C files into raspberry for study:

    Join files:
    $ tar -cvf joined.tar file1 file2

    Copy to pi:
    $ scp joined.tar pi@192.343.0.23://home/pi

    Unjoin:
    $ tar -xvf joined.tar

================================================================================

Fri Nov  6 06:45:45 EST 2015

    Code reading simple db to try to implement my own database and calc for c
    hashmaps are found in ~/study ...

================================================================================

Thu Nov  5 19:30:44 EST 2015

    Setting up raspberry pi from scratch:

    Hold "Shift" key during startup and install raspbian.

    Get wifi going by editing /etc/wpa_supplicant/wpa_supplicant.conf

    network={
        ssid="The SSID of router"
        psk="Your wifi password"
    }

    INSTALLING GO: 
    (from http://dave.cheney.net/2012/09/25/installing-go-on-the-raspberry-pi)

    Install prerequisites first:

    % sudo apt-get install -y mercurial gcc libc6-dev

    Cloning the source:

    % hg clone -u default https://code.google.com/p/go $HOME/go

    BUILD GO

    % cd $HOME/go
    % ./all.bash

    DID NOT RUN YET AS sudo apt-get update is not working right now in my pi.

================================================================================

Wed Nov  4 06:39:53 EST 2015
    
    My Redis-Martini Go sample is working at:
    // from https://gist.github.com/peterhellberg/9450839

    ~/go/src/redisko

    Used curl to test:
    
    $ curl http://127.0.0.1:3000/set/mykey?value=anyvalue

================================================================================

Mon Nov  2 12:47:50 EST 2015

    Trying out the chat example from :
    https://www.compose.io/articles/redis-go-and-how-to-build-a-chat-application/

    Get libraries:
    $ go get github.com/soveran/redisurl
    $ go get github.com/garyburd/redigo/redis

    Code is in:
    https://github.com/compose-ex/goredchat/blob/master/main.go

    My code is in ~/go/src/redisko/main.go

    Sample of redis (redigo) and martini:

    https://gist.github.com/peterhellberg/9450839

    Found redis.DialDefaultServer() from here:

    https://github.com/garyburd/redigo/blob/master/redis/conn_test.go

    DialDefaultServer() did not work.
    I used redis-url instead:

    https://github.com/soveran/redisurl/blob/master/redisurl.go

    redisurl.ConnectToURL("redis://127.0.0.1:6379")

================================================================================

Mon Nov  2 12:19:22 EST 2015

    Redis DB is getting me excited. Downloaded with wget:

    $ wget http://download.redis.io/releases/redis-2.8.23.tar.gz

    Downloaded an older version as I have an older Mac and OSX.

    $ tar xzf redis-....

    $ cd redis...

    $ make

    $ cd src

    Ran server:

    $ ./redis_server

    Ran client:

    $ ./redis_cli

    After some tinkering, I shutdown both client and server and my work was
    saved. This seems to be a good alternative to sqlite for my needs. It has
    lists, hashes, sets.

    The append-only file is an alternative, fully-durable strategy for Redis. 
    Edit redis.conf (usually in /etc/redis/redis.conf) if redis is installed.

    appendonly yes

    A chat application in go and redis:

    Source:
    https://github.com/compose-ex/goredchat/blob/master/main.go

    Article:
    https://www.compose.io/articles/redis-go-and-how-to-build-a-chat-application/

================================================================================

Sun Nov  1 07:31:56 EST 2015

    I read somewhere that learning programming should not be just from tutorials
    in the net. But as far as learning Go Martini web, this is a really sweet
    one:

    http://0value.com/build-a-restful-API-with-Martini

================================================================================

Thu Oct 29 19:40:55 EDT 2015

    Trying out martini go with sqlite 3.

    $ go get github.com/mattn/go-sqlite3

================================================================================

Tue Oct 27 21:40:33 EDT 2015

    Install Martini package (a go package for web development).

    $ go get github.com/go-martini/martini

================================================================================

Sat Oct  3 15:19:30 EDT 2015

    Finally solved the "undefined" errors on go. 

    $ go build -o {name}

    I had to re-install go with brew:

    $ brew install git go

    I ended up with a colorized git though.

    I do not care what happened to other installations. My golang installation
    runs and my git is colorized. Cool!

    Had to set $GOROOT(/usr/local/Cellar/go/1.4.2/libexec) and $GOPATH 
    (/Users/me/go).

    Calling "go run" is good for only one file, use "go build" for multiple
    files. Easier than building in C.

================================================================================

Sun Oct  4 07:31:47 EDT 2015
    To make go and vim environment rock, I enabled pathogen in vim, by adding
    "pathogen infect()" something in .vim/vimrc. It only works in my account
    and not root, but at this time I just want to code go in a non root account
    anyway so it works. Got the vim-go pathogen by following something from
    here: http://blog.gopheracademy.com/vimgo-development-environment/ . 
    Actually only these 2 lines:

    $ cd ~/.vim/bundle
    $ git clone https://github.com/fatih/vim-go.git
    
    I had to create "bundle" directory and another one. 

    Vim and go at work. 

    One caveat: everytime I save in vim, it autoformats which is great, but
    the vim "undo" feature goes only to the last save. So what I do now is
    to use git to commit (not even push to a server) and then I can do all
    my rollbacks from there. The good thing with git is that every commit
    will have a description. I can plan better and get to learn to use git
    more effectively now.

================================================================================

Sat Oct  3 14:27:08 EDT 2015
    
    Undoing stuff with git:

    https://github.com/blog/2019-how-to-undo-almost-anything-with-git

================================================================================

Sat Oct  3 13:37:04 EDT 2015
    
    After installing go on Mac with:
    $ brew install git go

    As of go 1.2, a valid GOPATH is required to use the `go get` command:
      https://golang.org/doc/code.html#GOPATH

    You may wish to add the GOROOT-based install location to your PATH:
      export PATH=$PATH:/usr/local/opt/go/libexec/bin

    ==> Summary
    /usr/local/Cellar/go/1.4.2: 4566 files, 155M, built in 3.8 minutes

================================================================================

Tue Sep 29 07:10:57 EDT 2015

    Taken from http://etodd.io/2015/09/28/one-weird-trick-better-code/:

    In summary, design data structures to match your specific problem. Don't 
    shoehorn a single concept into a bunch of separate, encapsulated objects.

    Next, write functions that leave the smallest possible footprint on that 
    data. If possible, write pure stateless functions.  

    That's the trick.

================================================================================

Sat Sep 26 08:55:57 EDT 2015

    Lesson learned: When studying from a book with code, code only from one
    place and have bookmarks only on one place of where your reading progress
    is. Not being able to keep track wanes interest. Keep track of progress
    so you can go on. This is what I will do now. Forgive myself for being
    sidetracked, but get the hell started again. Go on my OpenBSD is not so
    cool as I need root right now. I do not have the time to figure out how
    to configure it correctly so to hell with it. Start reading and coding. I
    will do JUST THAT! I will enjoy  the book now please. Dump the too techie
    stuff. In this case configuration is killing my learning. So just get rid
    of configuration problems and just code away. 

================================================================================

Mon Sep 14 21:50:47 EDT 2015
    
    Bought the book Go Programming Blueprints. I decided to just dive right in
    instead of getting stuck in internet tutorials or buying a beginner go book
    which can be very boring indeed. This book was a good choice. Dive right in.
    The author is also versed in TDD and that kind of stuff. "Modern" methodolo-
    gy, fun projects, practice by copying and tinkering with real code. Evolving
    small programs to be bigger and more functions. Understanding from the 
    explanation provided in the book.

    The only other resource I will use is the golang book in google which has
    small snippets...

    Installing go in OpenBSD 5.6:

        # export PKG_PATH=ftp://ftp.openbsd.org/pub/OpenBSD/5.6/packages/i386/
        # pkg_add 

    Installed go 1.3...

        $ go version

    This got a lot of errors.

    Can be solved with:

        $ export GOPATH=/home/go
        $ export PATH=$PATH:$GOPATH/bin
        $ ulimit -n 512
        $ ulimit -p 512
        $ ulimit -d 2036792

================================================================================

Tue Sep  8 06:15:17 EDT 2015

    Started clojure programming. Read some of this tutorial to start:

    https://aphyr.com/posts/301-clojure-from-the-ground-up-first-principles

================================================================================

Tue Sep  1 22:40:51 EDT 2015

    Will code now...

Tue Sep  1 23:17:08 EDT 2015

    I did about 2 and 1/2 10 minute coding sessions with 10 minutes rest in
    between. Got one little program running though. Will read and program
    file open and writing tomorrow.

================================================================================

Sun Aug  9 07:11:20 EDT 2015

    I read that working fast matters as the faster you finish something or you 
    expect to finish something, the less a barrier it will be to get it started
    and the less afraid you are to do it. So I created a directory to my current
    work to prevent having to try to remember what I was working on and then
    just get it done!

    Created a link to current work on C which is version 0.01 of git.

        $ ln -s study/git_study/git-0.01-src/ current_work

    To remove the link I could just do:

        $ rm current_work

    To go to the current work just:

        $ cd current_work



================================================================================

Fri Aug  7 14:32:47 EDT 2015

    I have been thinking a lot during the last shift of my main job of 3. I am
    already doing 3 jobs. I do not earn enough to be really financially free as
    although I earn more, I have a bit more expenses to cover to be able to do
    3 jobs like: 2 cars now instead of 1 and I had to buy a relatively newer van
    to replace our old van for the family, but this is an investment in my
    family's happiness. The second car will just let me go to other jobs or 
    appointments. It also gives me more freedom. Thus, both cars are an invest-
    ment. Two new phones and upgraded Julia's. So we now have 3 phones with all
    unlimited text and messaging. Also all needed to be able to communicate more
    with family and for working relations, finding jobs, Kenken's phone to keep
    his job and got him a little more freedom, which he needs and deserves. All
    again pluses.

    I figured out that once these all get paid up then I will have some wiggle
    room to help out the kids for school. I will also soon have to increase
    savings.

    With all this figured out, I then decided. Time to get started with my 
    dream of getting a tech/learning/programming group started. Sir Brizo will
    be a good resource. That is why I bought a cana kit raspberry pi. I will
    ship it on Saturday to Bohol and get this thing started.

    Lastly. I am getting a rhythm of getting my "paperwork" done. Managing more.
    Time to make a pact with myself. First 30 minutes and last 30 minutes of the
    day should be spent on writing and coding.

================================================================================

Sun Jun 28 18:12:58 EDT 2015

    Now getting the error:

        warning: incompatible implicit declaration of built-in function 'strpy'

    This also includes sprintf, strlen.....

    Solved this by adding #include <string.h> in cache.h.

    Now the whole thing compiles fine excluding a warning by the compiler to use
    snprintf() instead of sprintf() or strlcpy() instead of strcpy(). This might
    be something of an exercise next time, but the thing compiles. It's alive!

================================================================================



Sun Jun 28 15:43:32 EDT 2015

    Copying git-1.8.1-rc2 from my Mac to the BSD machine:

    $ scp user@192.168.0.15://User/user/user/working/git_tinker/* .

    Might as well start somewhere.

    Whoa! Able to compile git source 0.01 by including the proper libraries in
    Makefile. It has compiled successfully in my OpenBSD machine!

    In my Makefile:

    LIBS= -lssl -lcrypto -lz

    program_name: program_name.o
            $(CC) $(CFLAGS) -o program_name program_name.o $(LIBS)


    -lcrypto will include SHA and other cryptographic stuff it seems
    -lz will include zlib.

    Notice that $(LIBS) is placed at the end of the line (CC) line.


    Found a resource in www.zlib.net/zlib_howto.html and will run the sample
    program using "deflate()" and "inflate()" methods which gave the error:
    
    undefined reference to "inflate"

================================================================================

Tue Jun 23 20:17:43 EDT 2015

    Working on my Mac for a couple of days now for coding and recording entries.
    My BSD machine seems clunky nowadays especially as I had even more trouble
    trying to compile the git source code (version 0.01) on it. I might as well
    just program in Mac.

    The reason I am coding is an article from news.ycombinator.com about Elixir.
    I need to give this a try. And then work on the git source code and other
    projects.

    Installing Elixir:
    
    $ brew update
    $ brew install elixir

    ... now it is installing libtool, makedepend, openssl, libtiff, wxmac, jpeg,
    libpng, .... hung up...

    Unable to install Elixir. Back to C and Go coding. This sort of sucks.


================================================================================

Sun Jun  7 09:06:21 EDT 2015

    One week since the end of my Eddy VNA training ended... 7 weeks of hardcore
    schedules. Survived.

    April 17, 2015 - June 7, 2015. About 2 months of programming and journaling
    hiatus. A little bit of a rest. What I have been doing: 3 jobs, working out
    in the morning and tennis. I have to get into 5 minute journaling everyday
    and 5 minute coding also. Read 5 minutes. That makes 15 minutes of my day
    to programming and journaling. Sounds good enough. I can concentrate for 5
    minutes at a time. It will not eat all my day. 5 minute programmer. That is
    what I will be for now......

    FOLLOW UP:
    5 minutes journaling is great - just enough for quick entries
    5 minutes coding - if reading a bit then two 5-minute bursts works
            ( has to be short code though )
    5 minute reading......

    Well, that is it for now.
================================================================================

Fri Apr 17 21:10:51 EDT 2015
    
    > Code git origins
    > Code some cryptography (BSD libs used)
    > Code:
        - C implementation of encrypted database (simple)
        - Python implementation of "user interface" which will still be text
          (have to install python in BSD), Python simplifies coding of the
          user interface.

================================================================================

Fri Apr 17 21:06:46 EDT 2015

    One week of grueling 6/6:30 AM to 7/8 PM work. 6 - 7 at the nursing home and
    8 - 12 or 2 training for homecare. This will go one for 1 more month. Good
    luck to me. I sit all morning for training and am glad when I go to the 
    nursing home to do my PT work as it allows me also to stretch out, crouch,
    squat, lift, walk and run stairs. I shall keep my day job as a PT. Will just
    have a side job as something else.

    The weekend warrior is alive! Leave all my therapist worries behind and time
    to put my warrior/hacker hat on!

================================================================================

Mon Apr  6 21:15:38 EDT 2015

    Read from ycombinator news - Linus interviewed about GIT after 10 years. I
    downloaded the earliest git commit for git itself from: 

    https://www.kernel.org/pub/software/scm/git/


    Downloaded git-0.01.tar.gz and will study this. Easier to download from my
    Mac with Firefox right now but I scp'd it to my BSD machine:

    $ scp git-0.01.tar.gz baloi@192.168.0.13://home/baloi/baloi/

    Now will got through the source code and try compile it in BSD as it did
    not compile with Makefile on my Mac.
    
================================================================================

Sun Mar 29 09:30:40 EDT 2015

    I have decided that using vim-tmux for development might just be the best
    option for me right now rather than learning EMACS. I read something about
    Linus' development habits and he is said to change machines something like
    twice a year, wants a Linux distro that is easy to install and works out of
    the box, has not used Debian (I don't know if he has already today), created
    the kernel but says he might not be any good programming in "user space", 
    uses pine to check email and uses micro emacs only (with his tweaks) to 
    do development.

    This shows that Linus just wants to get to coding most of the time and not
    be bogged down with configuring systems - I had configuration nightmares 
    before that is why I left rails (setting up the libraries even with RVM at
    one time took too much of my time. I am not going to mess with that again.

    This will be the new mantra:
    > go near the computer
    > setup environment in less than 5 minutes (from scratch if everything is
      turned off) less than 1 minute of server is open... 
      Setup should include opening logs, journals, todos
    > CODE, music, code

    That is why this is my new setup:
    > standing "desk" room dresser with big mirror (clean table top)
    > OpenBSD development machine/server sitting at a corner downstairs on a
      standing desk in case I want to code there. (takes up less than 4 feet
      by 4 feet corner space without cluttering the view in the living room.
      The OpenBSD machine is like a sculpture.
    > Macbook Intel (older) plugged in and on the standing desk by room 
      dresser (easy to copy and paste links from this machine), have one
      Firefox browser open and two iTerm windows open (one ssh to BSD and 
      the other open to the local files that I have developed on this machine,
      mostly C now, some Python. 
    > Samsung Alpha phone with Pandora open (Linkin, S.U.N. project, etc) to
      keep the juices flowing. Email (gmail) and youtube accessed only through
      this gadget as it has faster internet, smaller screen (reminding me that
      email and youtube take lower precedence to programming on my Mac which
      has a bigger screen, but now a sometimes choppy internet connection.

    Evertime a coding session is done, I close my Macbook and tuck it in a
    corner, put any book in my bookshelf downstairs, unplug my phone if it is
    charging (tuck charger in its place), and maybe just close the "lid" of
    my BSD machine to put it into hibernate. My BSD machine will always be
    plugged in with a tmux session always open. 

    It is still nice to know that the BSD machine is still my central dev 
    machine which I can carry and charge with a very common Lenovo charger
    which I even have at work. 

    The music as whitenoise works for me too.
   

================================================================================

Mon Mar 23 22:30:39 EDT 2015

    Got the DES encryption with OpenSSL: example in C to run. 
    Code was gladly taken from: 

    http://www.codealias.info/technotes/des_encryption_using_openssl_a_simple_example

    It had this line:

    #include <openssl/des.h>

    The code sample instructions for compilation given was:

    $ gcc test.c -o test -lssl

    I had a bunch of errors after compling as mentioned above. It finally
    compiled with -lcrypto

    $ gcc test.c -o test -lssl -lcrypto

================================================================================

Mon Mar 23 17:44:56 EDT 2015

    Finished work @ 4:11 PM, went home, cooked pre dinner meal for family, 
    listening to Pandora / Linkin Park radio.

    openbsd.txt now has:
    
    baloi@192.168.0.21 

    Can ssh to OpenBSD machine. Cool! Trying to figure out DES encryption from
    GNU C library or OpenBSD/SSL. Trouble compiling BSD, still trying to figure
    this out. 

    already tried:

    $ gcc -Wall -o open_encrypt open_encrypt.c -lssl

    This produces "undefined reference" stuff though. Lots of it...

    Waiting for my encryption book to arrive. I might just end up hard coding
    all of it myself. Hope I have the energy even just to type everything from
    the book. Maybe just DES, which could end up to be a few hundred or k 
    lines.

    SOLVED !! Compile like this:

    $ gcc -Wall -o open_encrypt open_encrypt.c -lssl -lcrypto

    (Need -lcrypto)

================================================================================

Fri Mar 20 07:18:11 EDT 2015

    Need to study this program from antirez (fascinating little programs):

    https://github.com/antirez/linenoise

================================================================================

Wed Mar 18 22:45:35 EDT 2015

    Working and typing on the laptop keyboard from ottomans seem an ok position.
    It remains to be seen. Working out too.

    This will be the new programming setup. Just a laptop or a notebook, a radio
    and nothing else. Not even a calendar. They will all be at least 5 feet
    away. I will have my 8 x 8 feet of space to maneuver. Nothing readable in my
    corner. This works. The only thing that seems to right now. Give me this
    breathing space please.

    Maybe it should not just be close to a wall, but just a blank wall in front
    of you. This works. This definitely works.

================================================================================

Sun Mar 15 19:31:41 EDT 2015

    From Anteriz weblog (http://antirez.com/news/88): 

    "It is a few months that I spend ~ 15-20% of my time, mostly hours stolen to
    nights and weekends, working to a new system...."

    This is an eye opener for me. I am now earning enough money to support my
    family starting to save up for investment. I will invest time to get ready
    when enough money is there to build or nurture something.

    If I work at least 40-50 hours per week, I should have 8-10 hours for my
    side project. 8 hours seems good. 1 hour per day and then 4 hours in the 
    weekends...

    This is my new goal.

================================================================================

Sat Mar 14 07:06:53 EDT 2015

    I figured that using vim and tmux would give me the functionality I needed
    to be able to edit and basically do all other stuff in my laptop or at least
    be a reason not to go into emacs.

================================================================================

Tue Mar 10 21:39:31 EDT 2015

    Installing ports:

    # pkg_add wget
    # cd /usr
    # wget ftp://ftp.openbsd.org/pub/OpenBSD/$(uname -r)/ports.tar.gz

    # tar -zxvf ports.tar.gz

    # cd /usr/ports/sysutils/colorls
    # make install
    
    # vi .profile
    
    export PS1='\u@\h \w # `
    export TERM=wsvt25
    alias ls='usr/local/bin/colorls -G'
    :wq!


================================================================================

Mon Mar  9 23:56:02 EDT 2015

    To have color in the console:
  
    $ export TERM=wsvt25

    This may be added to .profile file. Colors! Sweet

================================================================================

Fri Feb 27 18:29:30 EST 2015

    Just 1 day more than a month after I've had this OpenBSD installation on my
    older Lenovo Thinkpad which I put alongside my oldish "more media" Macbook
    and I have learned a few things. Configured network, install/update driver
    for my wireless USB, have a console-only machine. Fun, fun, fun!


    It seems that the default shell for OpenBSD is the Korn shell /bin/ksh.
    
    The creator of Redis wrote that for the six years of developing Redis, he
    had quite a few side projects himself to keep his "juices flowing". Some-
    thing to break the monotony of one project, one code base. Distractions,
    scratching an itch. This is it.

    Now to figure out ksh....

    Downloaded vividchalk.vim using lynx. Then installed zip and unzip:
    # pkg_add -r zip
    # pkg_add -r unzip


================================================================================

Sun Feb 22 21:13:06 EST 2015

    No long-lasting headache since the 14th of February. Went on a week-long
    vacation 2/16-2/20/15 in Maryland Ocean City Hilton and Edroi's place in
    Frederick Maryland. Slept always by 9 or 10 PM. Ate well and not too often.
    A good vacation, although the new used car's AC had wrecked my airways. Had
    an asthma attack during the whole week, but was semi-manageable.

    Another possible headache cause would be the lack of sleep and the very late
    vigorous exercise.

================================================================================

Sat Feb 14 11:56:26 EST 2015

    I had another long-lasting headache yesterday (Friday). I went to the Y the
    day before and did the heated pool and sauna. I then did my kettlebell cycle
    11:30 - 12 am. I was not able to sleep early. It was also cold that night.
    Still cannot pinpoint the cause of the headache. Waiting for my Odyssey van
    to be ready today hopefully.

================================================================================

Wed Feb 11 23:42:59 EST 2015

    Worked out with kettlebells (basics of snatch - swing, getup, clean, press)
    some long cycle presses then finished with 4 rounds of kettlebell swings
    @35 lbs (30 sec with 60 sec rests). Enough to counter today's sitting at the
    wheel (driving) or so I hope.

    Working out with music helps though (S.U.N. project or similar).

    Workout was done after I finished my notes on Janjan's fast computer - 
    sweet !

================================================================================

Wed Feb 11 06:20:16 EST 2015

    Will work at 6:30 AM at Barnwell then 9 am at Ferncliff, back to Barnwell
    hopefully by 7:30 - 9:00.

    Follow up ( 11:40 PM ):
    * Worked @ 6:45 - 9 AM
      Ferncliff 10:05 - 5:45 PM
      Barnwell   6:45 - 9:00 PM


================================================================================

Tue Feb 10 22:34:27 EST 2015

    A stall on coding and even slowed down on workouts due to 2nd job just 
    started. First week of second job done. Tapering down now. Figured out that
    I just have to start at about 6 am and I must be ok....

    Now for my workout....

================================================================================

Sun Feb  1 18:47:39 EST 2015

    Just about done cooking dinner with Julia. Made re-baked chicken and minced
    cacciatori. We just also came home from YMCA and ALDI. We were waived the 
    fee for membership of $100 and this month is pro-rated at $40, it will be
    $88 next month. We will be able to reimbursed by our Blue Cross insurance.

    At the Y, I first played rebounder for the kids at the basketball court, 
    lifted a few kettlebell presses and did a lunge, pushup, run circuit at the
    track for about 3 rounds. Got me breathing harder. I then finished with the
    hot whirlpool and almost 10 minutes at the sauna. Really hot. Got me sweat-
    ing. Stress relief.

    Superbowl Sunday!

    

================================================================================

Sun Feb  1 09:50:44 EST 2015

    Maybe having python on my OpenBSD machine will be "too much tech". A little
    history of programming languages by year from Wikipedia:

    1968 - Logo
    1969 - B (forerunner to C)
    1970 - Pascal
    1970 - Forth

    1972 - C
    1972 - Smalltalk
    1972 - Prolog

    1973 - ML
    1975 - Scheme
    1978 - SQL

    1980 - C++
    1983 - Ada
    1984 - Common Lisp

    1984 - MATLAB
    1985 - Eiffel
    1986 - Objective-C
    1986 - Erlang
    1987 - Perl

    1988 - Tcl
    1988 - Mathematica
    1989 - FL (Backus)

    Of these, I want be stuck in the 70's when C was relevent and still is 
    today. Maybe a sprinkle of some other tech here and there.

    I keep thinking how 70's and 80's programmers, especially 70's kept the
    coding fire burning. Maybe with good tape recorded music.

    For me now: a headphone and a good playlist at medium loud.


================================================================================

Sun Feb  1 09:37:41 EST 2015

    I am currently using tmux on my OpenBSD terminal to be my "window manager".
    It does not get any sweeter than this. Pure text bliss. Everything is text.
    This is one way of looking at programming also, especially if you work with
    languages like C or Python. Open file, open socket, read file, read bytes
    from stream, write to file, search through lists, arrays, files, etc...

    Text processing in the modern world. 

    I still have my MacBook at my side for music and "eye candy" or to have any
    distraction. Keep distractions on another machine or even a tablet. 
    Internet for my BSD machine will be for git, ssh and scp. Should I remove
    lynx then? Yes, I just did.

        # pkg_delete lynx

================================================================================

Sun Feb  1 01:50:42 EST 2015

    Making wireless usb work:

        Connect to internet and update firmware:
        # fw_update
            // Cool! this updated wpi and urtwn

        Configure network

        # ifconfig urtwn0 scan      // gets the nwid (network id)
        # ifconfig urtwn0 nwid "network-id" wpakey "passkey"
        # dhclient urtwn0           // or dhclient wpi0 if urtwn0 configured as
                                    // above

    Git configure
        Generate ssh key and then copy to Mac
        $ cd .ssh
        $ scp id_rsa.pub user@ip_address://Users/username/directory

        Init repo
        $ git remote add origin git@github.com:baloi/repository_name.git
        $ git push -u origin master

    THIS WORKS!! Will now sleep happily...
      

================================================================================

    Error setting up wifi:

    ERROR:
        failed to load firmware urtwn0 urtwn18192cfwT

    This error came up when trying to do:
        # dhclient urtwn0
    
    But I only found this error in dmesg:

        # dmesg | tail

    That is after I still could not connect to wifi even after all the 
    configuration I tried alread. It got a bit bloody. I had to read the man
    pages which actually was very helpful. A person I worked who used to own an
    ISP and still works with Linux told me to try "ifconfig" and go from there.
    He specifically said to try ifconfig and read the man page. Duh! 

    I am sometimes tempted to read stuff from the internet before referring to
    the man pages so I get bits and pieces of things and sometimes miss the big
    picture.

    Having a barebones machine has enabled me to look at the system and its
    internals more now. I even downloaded the OpenBSD source and tinkered with
    "ed" the line editor's source code. From running make I learned how to 
    compile multiple c files with the "-c" option to first make the object files
    then try something like:

        $ gcc -Wall -o program routines.o another_object.o main.c

    Now to read the gcc man pages....

    Man pages say running gcc with the "-c" option tells gcc not to do linking,
    so the output will be object files output by the assembler.

    Warning: GCC man page spits out a LOT OF STUFF.

    "When you invoke GCC, it normally does preprocessing, compilation, assembly
    and linking. " - man pages for gcc

================================================================================

Sun Feb  1 00:49:21 EST 2015

    Mounting usb stick:
        # sysctl hw.disknames   // to get the name

    Get more info:
        # disklabel sd0

    Mount:
        # mount /dev/sd0a /mnt/sd0


================================================================================

Thu Jan 29 22:26:38 EST 2015

    Working out. Started at 9:50 PM. Stretched hips and shoulders. 2 rounds of
lifts now. Amazon music on. Slowly lowering volume of music and TV. Getting 
pumped also about my coding...

    Main function in main.c of link_list data structure project. Have structure
templates ready with function pointers for possible struct functions...

    I now have to figure out how to test and implement these functions. Then
eventually use this linked list to store some items...

    Eventually did 3 rounds of strengthening exercises....

================================================================================

Thu Jan 29 18:52:55 EST 2015

    Created local git repository for my tinkering with containers in C:

      * Create 'git' user
      * Login as git, make project directory and then initialize directory

        $ mkdir containers.git
        $ cd containers.git
        $ git init --bare

      * Login as your user and clone bare repo

        $ cd ~/working/
        $ git clone git@localhost:/home/baloi/git/containers.git
        $ git add .
        $ git commit -m 'first commit'
        $ git push origin master
 
    UPDATE: This currently works for me!

================================================================================

Wed Jan 28 22:06:34 EST 2015

    After downloading the OpenBSD source code, I checked out the bin directory
and surprised to find directories for the commands like cat, cp, chmod, date,
dd, ln, ls, md5, ps, rm, even ed!

    Go into directory like ed and just issue command:
        
        $ make

    Or it seems we can just compile eachline with:
        
        $ cc -02 -pipe -DBACKWARDS -c filename.c
          ....
          # do for all c files
        $ cc -o program_name 1.o 2.o 3.o

================================================================================

Wed Jan 28 19:01:34 EST 2015

    The kids are still at St. John the Baptist church basketball court for prac-
tice. Julia is sick from too much cold from yesterday's sledding and working 
today at very cold temperatures.
    To download OpenBSD code via cvs:
    
    # cvs -qd anoncvs@anoncvs.ca.openbsd.org:/cvs get -P src

================================================================================

Tue Jan 27 21:59:25 EST 2015

    Standing while reading the book "The Unix Programming Enviroment". Ordered
Kernigan and Ritchie's "The C Programming Language". I want to work on the
samples there. Getting interested in the standard C library functions.


Tue Jan 27 19:24:29 EST 2015

    Finished workout in 40 minutes. Mostly dancing to 3 tunes free from Amazon:
Personal Jesus, Gonna Make You Sweat(Everybody ), The Power (Snap).
    Had a good dinner (shrimp, pork ribs menudo with atay, and pork curry. Also
cleaned some dishes with Janjan. Janjan regularly washes dishes. Bless him.


Tue Jan 27 18:02:14 EST 2015

    I finished work and went to Hannaford with Julia and Kenken. Spent $43 plus
Julia spent $15 on more food from Stewarts. More extra expenses. Good thing we
have something in the bank, but extra stuff has to be tapered starting now. 

    Going to work out in 5 minutes. Planning to do 30-45 minutes. Having a cut-
off for workouts is good so I know how to allot time for the task.
    Going now!

================================================================================

Tue Jan 27 07:41:04 EST 2015

        Installing packages:

        * Connect to LAN
        * # export PKG_PATH=ftp://ftp.openbsd.org/pub/OpenBSD/5.6/packages/i386/
        * # pkg_add vim

        Works!

        Setup global vimrc file:
        
        * # cp /usr/local/share/vim/vim74/vimrc_example.vim /usr/local/share/vimrc

        Install git:
        * # pkg_add git


================================================================================


Mon Jan 26 23:00:09 EST 2015
        
        This will be my log of what I have done with my BSD machine. I just 
installed this from my flash drive by doing the following:

  * downloaded install56.fs the OpenBSD website

  * erased contents of a flash drive using GUI diskutil

  * use command line diskutil to get current list of devices
    $  diskutil list

       // my flash drive was /dev/disk1

  * unmount flash drive
    $ diskutil unmountDisk /dev/disk1

  * wrote install56.fs to disk
    $ sudo dd if=install56.fs of=/dev/rdisk1 bs=1m

        // Note that using /dev/rdiskN instead of /dev/diskN may be faster

  * eject
    $ diskutil eject /dev/disk1

  * restart machine you want to install OpenBSD. Make sure that your flash drive 
is plugged in during boot.

        // Note: 
        //      Installation was easy and added user. Did not connect to the
        //      internet yet. This will be for the second install. gcc was 
        //      installed by default with vi also - makes it good. I just could 
        //      not find the sources yet. Maybe sources are not installed by 
        //      default. Installation took much less than 30 minutes. Felt like 
        //      10 minutes.

        Currently only vi and not vim is installed. No syntax highlighting, no
        auto complete, no expandtab, no retab. Bare bones. No Python even.

        Am I in trouble or what? "!!date command in vi works though for 
        timestamping so I am doing something right.

================================================================================
