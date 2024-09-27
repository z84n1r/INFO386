java c
INFO386 T1 2022 
Workshop 2 
Apache   - Web   Server 
Getting Started
For this workshop you will   need to   connect to your Virtual   machine. The   instructions to   do this   are   in workshop Guide   1. As   in Guide   1,   you will   have to start your Virtual machine and   connect   via   RDP.   If the IP   has changed, you will   need to download a   new   RDP   file.   Once   you’re   within your   Virtual   machine,   we   can start setting   up Apache. A   reminder that we are   now   working   exclusively   within   the   VM,   you shouldn’t   be downloading any files to your   main device,   and   any   instructions that   are   specifically   for   outside of the VM, will explicitly   say   this.
Make sure, that you   have already downloaded the files from   last   workshop:
•            C++   (VC_redist.x64)
•          Apache   (httpd-2.4.46-win64-VS16.zip)
Setting   up Apache 
Unfortunately, the Apache download does   not come with   its   own   installation wizard,   so   we   have   to   do   some   manual setup. This will start with   unpacking Apache,   moving   it to the   desired   location,   and installing   it   using command   prompt.
Unpacking and   moving Apache folders 
First, find the Apache zip file.   It should   be   in the   downloads   folder. This   compressed   folder   can   be   extracted   by selecting Compressed   Folder Tools and extract   all.  
Figure 1: Apache zip   file
The download folder works for our   purposes so   confirm the   extract   file   location   by   selecting ‘extract’   .   This   may   take   sometime.
In the   meantime, the default settings for Windows   10   hides some file   extension   names.   It’sagood   idea   to   make sure you can see these. To   unhide these,   use the   windows   search   bar to   find ‘   File   Explorer Options’ as   shown   in   Fig   2.
Figure 2:   Folder options
You can then deselect   hide extensions for   known file types   as   shown   in   Fig   3. With   this   deselected,   files   like text documents will show   .txt   in their   file   names.  
Figure 3: Hide extensions for   known file   types
Once the Apache extract   is complete, we will   be   able to   see three   items   including   the   folder   Apache24   and a   ReadMe text document as   shown   in   Fig   4.  
Figure 4: Extracted Apache filesWhile the   ReadMe   is   useful, for our   purposes we only care   about the   Apache24   folder.   It   contains   the      actual code to   run Apache.   However, the configured   location for Apache   is   in the C:\ drive root   folder.   As such,   right click and select ‘copy’ on the Apache24 folder shown   in   Fig   5.  
Figure 5: Copying Apache24
With the Apache24 file copied, navigate to the C:\ root folder   by   entering   C:\   (Highlighted   in   Fig   6) to   the   navigation   bar and   hitting enter.
Figure 6:   Navigating to the C:\   root folder
Once   in the   C:\   drive   root folder, you can   paste the folder   by   right clicking   and   selecting paste.   With   Apache24 added, the   root folder   should   look   like   Fig 7.  
Figure 7: C:\   Root   drive with Apache24
Now that the Apache24 folder   is   in the   right   place, we can start   examining   the   contents.   Double   clicking on the folder should   reveal a whole   host of files   and   text   documents   as   shown   in   Fig   8.  
Figure 8: Apache24 folder contents
Installing Apache 
While the folders are   in   place, Apache   is   not yet functional. We   can   prove this   by   simply   visiting the   local   version   of   your   website   via localhost/in   your   web   browser.   Doing   so   will   produce   the   error “Hmmm   … can’treach   this   page” as   in   Fig   9.  
Figure 9: Can’t yet   reach   localhost executing code.
Later, once we   have completed our setup, visiting   localhost   will   allow   us   to   view   the   page   that   will   be   served over the   internet   by Apache.
With all the files   in the   right   location, we can   start with   running command prompt as   an administrator as shown   in   Fig   10.  
Figure 10:   Running Command   Prompt
The command   prompt acts as a   terminal   or   shell.   We   can   use   it to   input   commands   to   perform   advanced   administrative functions.   Make sure to   run   it as an administrator. You   may   have   used   it   before,   but   if not, the opening screen should   look   like   Fig   11.  
Figure 11: Command   Prompt
Command   line   provides a   lot of options. We want to   use   it   to   run   an   installation within   the   folders   we   moved   before.   However, the default directory for command   prompt   is   not that   folder.   We   can   test   this   by   inputting the command “ DIR/w”   (Directory   in the wide format)   into the command   prompt. This shows the content of the current folder   (Fig   12). As you   can   see,   the   contents   of this   folder   are just   the   default set for our Windows   10   Image.   Note that the   administrator   username   will   be   different.  
Figure 12:   Default director代 写INFO386 T1 2022 Workshop 2 Apache – Web ServerC/C++
代做程序编程语言y
We can   use the CD command followed   by the   desired   directory   to change directory.   In   this   case,   the desired directory   is C:\Apache24\bin . We can once   again   check   this   by   inputting the   command   DIR   to show the directory. This time   it should contain   a   number   of files,   starting with   ab.exe   and   ending   with   zlib1.dll as   shown   in   Fig   13a.
Figure 13a: Apache24   bin directoryIn this folder we want to   run the   install for   httpd.exe, so   we   input the   command “ httpd.exe -k install”   as   shown   in   Fig   13b. Windows   Defender   Firewall will also   block some of the functionality   for   Apache,   so   we   will   need to allow access as shown   in figure   14.  
Figure 13b:   httpd.exe -k   install  
Figure 14: Windows   Defender   Firewall
Allowing access will complete the   install.   However,   it won’t give any   confirmation.   To   test   if   it   worked,   we will first   need to start Apache.
This can   be done with the command “ httpd.exe -k start”   as   shown   in   Fig   15.  
Figure 15: Starting Apache
Once again, this won’t give any   indication of   system   status.   However,   we   can   check   localhost   to   see   if   the website   is   now working.
If the   install worked   properly, this should   now give the ‘It works!’ website   as   in   Fig   16.
Figure 16:   Localhost with Apache
With this done, Apache   is   now set   up and   it   can   respond to   any   requests   it   receives.   You   can   now   close   the command   prompt.
Altering the website
The website setup   by Apache   is   very   primitive, containing only   the   header “It works!”   .   We   can   improve   this   by going to the Apache24 folder   (in the C   Drive)   and   into   the htdocs folder   as   shown   in   Fig   17.  
Figure 17:   Navigating to   htdocs
Inside the   htdocs folder, you can   now see the ‘index.html’ file. This   is the   website   Apache   served   up   at   localhost.   If you   installed a text editor, you can open   it   using that.   Otherwise,   you   can   edit   it   with
Notepad   by   right clicking and selecting   open with.  
Figure 18 Opening   index.html with   notepad
Then select ‘Choose another app’ as   in   Fig   18   and    ‘ More options’   and   ‘Notepad’   as   in   Fig   19.
Figure 19:   More apps and   Notepad
As you can see   in   notepad or your text   editor   of   choice, the   html   code   for   the   website   is   extremely   basic.
You can change this as desired,   but   for   the   guide   we   will   add   a   title to   the   page   by   adding “Info386 Workshop 2” to the html as   in   Fig 20.  
Figure 20:   Editing   index.html
With this code, your   localhost should   now   include the title for the tab   as   in   Fig   21.  
Figure 21: Working   html title
Starting and stopping   apache
Previously, we started Apache from the command   prompt. While we   could   start   and   stop   Apache   from   command   prompt, Apache also   has an optional ApacheMonitor.exe file   in the bin file   as   shown   in   Fig         22.  
Figure 22: Sending ApacheMonitor.exe to desktop
We can create a shortcut on   the   desktop   to   open   this   more   easily   later.   Once   you   have,   double   click   to   run the file. This will   produce an alert   as   Microsoft   Defender   blocks the   application. To   allow   it,   click
‘ More info’ and ‘ Run anyway’ as   in   Fig   23.
Figure 23: Allowing ApacheMonitor.exe
With   it given   permission to   run, we can   now see   it   amongst the   hidden   icons   as   shown   in   Fig   24.   From   here, we can start, stop,   and   restart   our Apache   server.  
Figure 24:   Using ApacheMonitor.exe
You can then   use the functions on the   right of the   Service   Monitor   to   start   and   stop   your   server.  
Figure 24b: Start and   stop   your   server
With this done, you can   manage Apache as   needed   within   your   Virtual   machine.   However,   due   to   the   network settings of the Virtual   machine   it   is   not yet accessible from   the   internet.
Note that the website   is only accessible when your Virtual   machine   is   on   and your   web   server   has   been   started   in ApacheMonitor.exe.
Next week, we will   build the database   layer of the   stack   and work   on   some   PHP.   Don’tforget   the   workshop quiz available at the   end   of the   week.
Challenges
You can also attempt the following   challenges:
•             With our current   network settings,   command   prompt   cannot ping the   Virtual   machine.   Find out why and change the   network   settings   to allow it to   be   pinged.
•             Using a combination   of   HTML,   CSS,   and   optionally   JavaScript,   create   a   website
celebrating a   hobby of yours   in the   htdocs file. You   may   have   to   refresh yourself on   this   viahttps://www.w3schools.com/ 
If you created a website for the   previous guide, you   can   use   that   as   well.







         
加QQ：99515681  WX：codinghelp
