java c
INFO386 T1 2022
Workshop   3
PHP and   mySQL
Getting Started
For this workshop you will   need to   connect to your Virtual   machine. The   instructions to   do   this   are   in   workshop Guide   1. As   in Guide   1, you will   have to start   your   Virtual   machine   at   azure.labs.com   and   connect via   RDP.   If the   IP   has changed, you will   need to   download a   new   RDP file.   Last week, we   setup   Apache and   now we will continue to   build your   website   using   PHP   and   mySQL
Your website
Once you’ve connected via   RDP, all you   need to   do   is   run ApacheMonitor.exe   as   shown   in   Fig   1.   If you   did   not create ashortcut for this file, the file   itself   is   in   Apache24\bin.   
Figure   1: ApacheMonitor.exe
Once you   have   run this file the Apache server should   be   up. You can   confirm   this   by   first   checking
localhost/   in your   local   browse as shown   in   Fig 2.   If you’ve   customised the   website   in   the   last   workshop,   the customisations should show   here.   
Figure 2:   Localhost
Changing the   DNS/Host   Name
While we cannot change the   DNS of the   site, we   can   edit   the   ‘hosts’   file   on   the   machine,   which   the   browser checks   before   initiating a   DNS query.   By editing   this   file,   we   can   override   with   any   host   name   and thus access the site through a   new   host   name,   other   than   localhost\
Open   up the   hosts text-file at C:\Windows\System32\drivers\etc   
Figure 3a:   hosts folder
Add a   new   line to the   bottom of the code,   using   the   default   IP   address   for   any   device   127.0.0.1   and   the string you want as your   new   host   name, we suggest you   use your   first   name   so   that   your   group members will   be easily able to access your   site   from   their   VM. This   is   how   you   will   be   able   to   link   your   research for the final   project.
Your final   line of code should   look   like: 127.0.0.1         
Figure 3b:   Editing the   hostname
PHP:   Hypertext   Preprocessor   (PHP)
PHP:   Hypertext   Preprocessor   (PHP)   is an open-source scripting   language. While   it was   originally developed for the creation of   personal   homepages   (Its original   acronym),   it   has since   become   a   staple   of online websites.   In   2020,   it was still   run on78.9%   of all   websites.   It   is   also   a   prerequisite   for   running   MySQL and WordPress. As such, the first goal   for this   guide   is   to   install   PHP.
Downloading   PHP
The first step of this workshop   is to download   PHP   within   your VM. To   do   this,   visitwindows.php.net/downloadThis website will   present you with the download   links for   PHP 8.1   in   a   variety   of   different   formats.   We      need to   download the 64bit thread safe zip file   for   PHP   as   shown   in   Fig   4.   64bit   because   the   VM   Image   runs on a 64bit operating   system   and thread   safe   because Apache   utilizes   multiple   threads.   
Figure 4:   PHP 64bit thread   safe   zip
The zip file should   be   named   php-8.1.5-Win32-vs16-x64.zip as shown   in   Fig   5.   
Figure 5:   PHP Zip   downloaded
Once the file   is   downloaded, we   need to extract the file. Just   like the   httpd.zip   file,   simply   select   Compressed   Folder Tools, extract all,   and   extract.
Next, copy   the   extracted   php-8.1.5-Win32-vs16-x64 file   to   the   C   drive   (Navigate   with   C:\   in   the   navigation   bar   at the top).   Rather than   use this   bulky   name   in our configuration,   rename the folder   to   PHP   as   shown   in   Fig   6.   
Figure 6:   Renaming   php folder
Configuring   PHP   in the system environment
With the   PHP folder   now   in   place with the   name   php we   now   have to   give   it   permission to   run   scripts   outside   of   the command   line. To do this, we   need to   open   up the   system   environment   variables.   Search   Windows   for environment variables and select ‘Edit the system   environment   variables’   as   shown   in   Fig   7.   
Figure 7:   Find ‘Edit system environment variables’
From these settings you can   navigate to ‘advanced’ and   ‘Environment   Variables’   as   shown   in   Fig   8.   This   will   present   a   list of   user variables   and system variables   as shown   in   Fig   9.   
Figure 8:   Finding   Environment Variables
From the   Environment variables   menu, select the   user variable   Path   and   Edit. This should   show   only   one   path.   
Figure 9:   User variables and   System variables
To   add a   new   path to the   user variables, select ‘New’, enter “C:\php”,   and   select ‘Ok’   to   confirm.   
Figure   10:   New   path for C:\php
Configure Apache for   PHP
With   PHP added to the environment, the only   remaining step   is   to   configure   Apache   to   accept   PHP   when   running the server. To do this, we   need togo to the   Apache   file   httpd.conf   located   inc:\apache24\conf
This file can   be opened with   notepad   by   right clicking, selecting   open with,   More   options,   and   selecting   notepad. Alternatively, you can open it with your   downloaded   text   editor   of   choice.         This should   look   like   Fig   11.   
Figure   11:   httpd.conf file
As described   in this file,   it   is the   main Apache configuration file.   Note that ‘#’   declares   the   line   a   code   comment.
In this file, we will   be adding four   lines of code   to   the   top   of the   file.   The   code   is   as   follows:
AddHandler application/x-httpd-php   .php
AddType application/x-httpd-php   .php   .html
LoadModule   php_module   "c:/php/php8apache2_4.dll"   PHPIniDir   "c:/php"
These   lines set the   handler for   PHP, sets the type for   PHPand   html files   (PHP   can   run   HTML),   loads   the   .dll file to   manage the files and specifies the   directory to   find   the   PHP   .ini   file.
Save this with “Ctrl+S” or   “Command+S”   .   This should   look   like   Fig   12.
Figure   12:   PHP added to Apache   httpd.conf file
Next, we   have to set the   php.ini file for Apache to   use.   Fortunately,   PHP   comes   with   .ini   files   to   use   for   this, we just   have to   pick one and   rename   it. To   do this, we   navigate   back to   C:\php to   find   php.ini-development   as shown   in   Fig   13.   
Figure   13:   php.ini-development
Now,   rename the file to   php.ini   (Remove “-development”)   by   right clicking and selecting   rename   as   shown   in   Fig   14.   
Figure   14:   Renaming   php.ini-development to   php.ini
This will give an alert stating that   the file   may   become   unusable   if   the   extension   is   changed.   Select ‘Yes’ to confirm   the   change.   
Figure   14: Confirming   rename to   php.ini
Once the file   name   is changed, the   icon will also   change   to   a   gear   over   a   piece   of   paper   as   shown   in   Fig
15. You   may   need to   refresh the explorer to see   this.   
Figure   15:   New   icon for   php.ini
With this completed, all the files are   correctly   set   up. We   simply   need to   restart   Apache   and   it   will   apply   the changes. To do this, goto the ApacheMonitor   controls   in the   bottom   right   as   shown   in   Fig   16.   
Figure   16: ApacheMonitor controls
Simply click the ApacheMonitor.exe   icon,   hover over Apache2.4, and select   restart.   Ifthe ApacheMonitor   icon   is   not   in the group,   run the ApacheMonitor.exe shortcut that was   created   in      guide   2.   If this   produces an error   (“The   requested operation   has failed”), you   may   have to   install   the   x86 version of   PHP.
Using   PHP
The   main   purpose of   us   using   PHP   is   not to   manually code   PHP,   but   rather to   allow   MySQL and
WordPress.   However, we can still   use   PHP   in the current version   of   our website.   This   will   allow   us   to confirm that   it   is working as   intended. To add   PHP,   navigate to the   htdocs folder   in   Apache24
(C:\Apache24\htdocs).   Here,   right click   index.html and open   it with your text   editor   (Default   notepad).   
Figure   17:   Opening   index.html to add   PHP
Once open, we should seeyour   modified   html file from the   previous   guide.   If you   have   not   modified   it
for the challenge,   it will   look   like   Fig   18.   
Figure   18:   Index.html
To test this, we’re going to   put   in the following code   before the   closing tags.
echo   "This is   PHP";   ?>
Once   inserted, this should   look   like   Fig   19.   
Figure   19: Adding   PHP to   index.html
Now that we   have   PHP   in the   index.html file   in Apache, we can visit   localhost. Visiting   localhost   we   should   now see the   printed text “This   is   PHP” as shown   in   Fig   20   and   Fig   19.   
Figure 20:   PHP working   in   localhost
MySQLWith   PHP   installed, we can   now   install   MySQL. SQL stands for Structured   Query   Language.   We   will   be   using   it to create and   manage   a database. WordPress   will   also   use   a   MySQL   database   to   manage   the         blog   posts and   user accounts.
Installing   MySQL
Unlike with the   manual Apache and   PHP  代 写INFO386 T1 2022 Workshop 3 PHP and mySQL
代做程序编程语言 install, we will   be   using   an   installation wizard   for   MySQL.   You   can find this on the following   link.
https://dev.mysql.com/downloads/windows/installer/8.0.html
This will   bring you to a download   page for the   MySQL   Community   downloads   as   shown   in   Fig   21.   
Figure 21: Community   Downloads   MySQL   InstallerOn this   page,   it shows several download options.   Select ‘   Download’ for   Windows   (x86,   32-bit),   MSI   Installer   as shown   in   Fig 21. The website will then suggest   Logging   in   or   creating   a   new   account.   We   want to skip   past this and click ‘No thanks, just start   my   download.’   as   shown   in   Fig   22.   
Figure 22: Confirming   MySQL   Download
Next,   run the file. The file should   be   named   mysql-installer-web-community-8.0.28.0.msi as shown   in   Figure   23.   
Figure 23:   MySQL   Installer file
Once the download file   has   run,   it will   popup with the   installer.   It   may ask   you   if   you   want   to   update   the   installer as shown   in   Fig 24. Select ‘   No’ to   continue with   the   installer.   
Figure 24:   Denying optional   MySQL   Installer   Upgrade
Once   it   has finished the   installer will   have you select the desired   Setup Type   for   MySQL.   We   want   to   select ‘Server only’ as we will   be   using   it for   our web-server   backend.   
Figure 25: Setup Type   Server   Only
With the Setup Typeset to server only, we can   confirm the   download   of   MySQL   Server   8.0.23   by
selecting   Execute as shown   in   Fig   26.   
Figure 26: Confirming download of   MySQL   Server   8.0.21   As the   installer downloads,   it will show the status   as   in   Figure   27.   
Figure   27:   MySQL   Download Status
Once the status   is complete   as shown   in   Fig   28,   you   can   continue   by   selecting   ‘Next’   .   
Figure 28:   MySQL   Installation Complete
This will   bring you to the configuration wizard. Select ‘   Execute   as   shown   in   Figure   29 to   start   configuration.   
Figure 29:   MySQL Start   Configuration
Once the   install   is completed, you will either   have the   Installer automatically   appear:   
Or, you can goto the Windows start   menu and   launch   MySQL   Installer -   Community   as   shown   in   Fig   30   
Figure 30:   Start   Menu   Select   Reconfigure to   re-enter the   MySQL   Installer
Under Type and   Networking we want to change the   Config Type from   Development   Computer   to   Server   Computer as   in   Fig 31. Once this   is   done,   proceed to ‘Accounts   and   Roles’   by   selecting ‘Next’   twice, ignoring Authentication   Method.   
Figure   31: Config   Typeset   to   Server   Computer
At the ‘Accounts and   Roles’ section, you will   need to   set the   MySQL   Root   password   as   shown   in   Fig   32.            You will   need to   have this   password to   use   MySQL for this workshop and to   set   up   WordPress   in the   next   guide. Since the data we will   be   collecting   is   not   particularly   sensitive, you   can write   down   the   password      in a   note.   If you   lose this   password, you will   need to   reinstall   MySQL and will   lose   all your   database data.   
Figure 32:   MySQL   Root   Password
Once you   have   done this, select   next   until you are at ‘Apply   Configuration’   as   shown   in   Fig   33.   Click   execute as shown   in   Fig   33.   
Figure 33: Apply   MySQL Configuration
Once you   have clicked execute, the   installation wizard will show   it’s   progress   as   it   applies   the configuration and   initializes the database. This should take only   a   few   minutes.   Once   each   step   is ticked,   the   Finish   button should appear as   in   Fig 34.   Once this   is   done,   select ‘Next’   on   the   product   configuration   page and ‘Finish’ on the   installation complete   page.   
Figure 34:   Finish   installing   MySQL
Creating a   database
With   MySQL downloaded, we can go about   creating   a   database. To   get   started, we   need   to   open   up               the   MySQL Command   Line Client. To do this, simply search   windows   for   MySQL   and   select   MySQL   8.0   Command   Line   Client as shown   in   Fig 35.   
Figure 35:   Opening   MySQL 8.0 Command   Line Client
Opening this file will   immediately   prompt you to enter the   MySQL   Root   Password as   shown   in   Fig   36.   
Figure 36:   Entering   MySQL   Root   Password
Correctly entering the   password will show the copyright   and   help   commands   as   shown   in   Fig   37.   
Figure 37:   MySQL   Command   Line   Client   Logged   InWith the   MySQL Command   Line Client open we   can   start   creating   and   manipulating   databases.   Note   that   MySQL is case sensitive, so   a capitalised   letter   included   in   a   name   must   be   referenced   later   as   a   capital.
The first thing we can do   is create   a   database for   the   workshop   with the   command:
create database workshop;
Entering this will output   Query   OK,   1   row   affected as shown   in   Fig 38.   
Figure 38: create   database workshop;
After creating the workshop,   MySQL   does   not   move   us   into   it   immediately. We   need to   do that   manually   with the command:
use workshop;
This will   produce the output   ‘Database changed’ as shown   in   Fig   39.   
Figure 39:   use workshop;
To see the tables within this database, we can   enter   the   following   command:
show tables;
As we   have   not added any tables, this will output “Empty   set”   as   shown   in   Fig   40.   
Figure 40: show tables;   A database   is worth   little without data, so   let’sadd   some.
Adding   data
We will start this   by adding a table.   We   will   be   including   in   this   table   5   different   fields:
•                                  A   unique   User   ID
•                                    First   Name
•                                    Last   Name
•                                  GPA Score   •                                 Age
If you took   INFO151,   much of this will   be familiar to you.
For this we are going to want   a   multi-line   command to set   these   attributes.   Make   sure   to   keep   these
attribute   names   lowercase. To enter a   multi-line command, you can   press   enter   at   the   end   of   each   line.         MySQL allow you to   keep add   new   lines without   running the   command   up   until you   add   in   a   semicolon   ;.
Once the semicolon   is   input,   it will   run the   previous command.   Enter the command   in   Fig 41 to create the   table.   
Figure 41: Create table students
As when creating the database, this will   output ‘Query   OK’   as   shown   in   Fig   42. The   time   may   differ,   this
means that the operation took a slightly   different   amount   of   time   and   is   not   a   cause for   concern.   
Figure 42: CREATE TALE students
Now with the tables created, we   need to fill   our tables   with   details   of   a   student.   Follow   Fig   43   below,
and   be sure to order everything correctly,   as VALUES   will   be   placed   ordinal   respective   to   what   order   you   selected for the columns. This   means that   if you   put   Rabbit   first,   Rabbit will   be the first   name   (which we      do   not want):   
Figure 43:   INSERT   INTO students
If this was   input correctly,   it will output ‘Query   OK’   as   before,   but   with   1   row   affected. This   row   is the   data we   have   added.To check that this worked as   intended, we   need to write   a   query   to   select   everything   from   the   students         table. To   do this, we write the command shown   in   Fig 44.   Note   that   *   acts   as   a ‘wildcard’   and   represents   everything.   
Figure 44: Select   *   FROM students;
Once you’ve entered this command,   it should output   an   ascii table   with   the   data   shown   within.   
Figure 45: Output of selecting   all from   students
If you want to add   more data, simply   repeat the   command   in   Fig   43   with   different   values.
This   manual   process of   managing data   is somewhat cumbersome.   It   can   be   made   more   comprehensive   using applications such as   phpMyAdmin.   Fortunately, for our   use with   WordPress,   WordPress   will   be
managing   MySQL without   us   manually entering values   into the   database.   However, to get   this   set   up   we   will   need to start guide 4   by setting   up a   MySQL   account   and   database   to   use.
This   is the end of this   week’s   guide
Challenges:
If you want to an extra challenge, try   the following   challenges:
•             Use   PHP to create   a field   where   a   site   visitor   can   enter   their   name   and   have   an   alert   greet them   using the   name they entered.
•             Create a   new database of   workshop   guides   including   attributes   such   as   guideNumber,   Program, difficulty, and fun.   Make sure to   use   appropriate   data types.
Both of these   may   require extra   research. You   may want to   use aresource   such   as   w3schools.
https://www.w3schools.com/sql/default.asp         https://www.w3schools.com/php/default.asp

         
加QQ：99515681  WX：codinghelp
