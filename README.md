java c
INFO386 T1 2022
Workshop   1
Azure - Virtual   machine
Introduction
Welcome to your first   INFO386 Workshop! These guides are designed   to   help you   construct   a   web
server on a Virtual   machine. They will   provide step-by-step   instructions   of   how to   construct   a   basic web   server. While you can add flourishes on top   of   what   is   instructed   here,   you   are   expected   to   be   able   to   use this   content.
Azure - Virtual   machine
Microsoft Azure   is a set of   cloud   services   hosted   and operated   by   Microsoft.   For   more   information on cloud   computing,   look for the weekly content on Blackboard.   For the   purposes of the workshops, the service   used   is Azure’s   hosting of Virtual   machines   (VMs).   For this course we will   have you operate   one   of   these Virtual   machines.   It   is on this VM that the web server will   be   hosted   using a WAMP server   stack.
Figure   1:   Microsoft   Azure   Logo
WAMP - Server   Stack
A server stack, also   known as a ‘solution   stack’,   area   set   of   software   subsystems/components   which   together create a   platform. that fully supports the   desired   application.   In this   case, the   desired   application   is the web server you will create. The   INFO386 workshop   guides will   cover   the   creation   of   this web server   using the WAMP software stack. The   acronym WAMP   stands   for   Windows,   Apache, MySQL, and   PHP.
These four components   have   the following   purposes for the web server   platform.	
●          Windows: This   is the   base   operating   system   on   which the   web   server   will   run.
●          Apache: This   is the   server   software that   is   responsible   for   serving   the   web   page   when   a   request   is   made.
●             MySQL: This   is the database   management system that stores   data for your   website   to   use.
●             PHP: This   is the scripting   language which will facilitate   more variable components   of the   website.
On top of these core components of the WAMP   stack, we   will   be   using   WordPress,a   content-   management system   used to support   personal   blogs.
This guide, as the title suggests, will   cover the   basic   setting   up   and   using   your   Azure   account   and   Virtual   machine on which the web server will   be   hosted.
Getting Started with Azure   Labs
What   is a Virtual   machine?
Virtual   machines allow you to   run an operating system   in   an   application   window   on   your   desktop   that   behaves   like a full, separate computer.   It can   also   be   done   using   cloud   computing,   allowing you   to   control the Virtual   machine   (VM) from wherever you   have an internet   connection.   For   our web   servers,   we   have already created template VMs for you to   use
Activating your Azure Account
Go   to   labs.azure.com   and   login   using   your   VUW   student   account
After   logging   in, you should see this screen, depending   on your   inquiry topic   group:   
Figure 2:   Microsoft Azure   Labs   landing   page
Ensure your virtual   machine   is   running,   by   using the   blue toggle   in the   bottom   left. This starts the   machine, and can take   up to   3   minutes each   time.
If   nothing   is showing on your dashboard, check your   student   email   for   an   invitation   and   follow   the   link   to confirm your   access.   
Figure 3: Account   registration   email
Configuring your Virtual   machine   (Basics)
As we   have   used a template VM, the configurations for your VM   have   already   been   chosen.   Our Virtual   Machines   have the following configuration:   
Figure   4:   Default   ‘basics’ settings.   The   image   (OS): We are   using Windows   10
Size   (Hardware size): This   impacts several factors; the   processing   power,   memory, storage capacity,   and   the   main determining factor for the   price. We   have chosen   a   relatively   smaller   hardware   size,   as your VM will only   be   running a   simple web   server.
Cost to   run the   machine.   Don’t worry,   this   is covered   by the course,   but   an   important   consideration   if   you were going to   build your own VM.
Operating your Virtual   MachineNow your   machine   is   running, we   need to connect to   it   using an   RDP   connection. To   download   the   RDP      file, click the   blue computer   in the   bottom   right. This will download   a file   to   your   device,   which   includes   the   information for the   IP Address and   port   number for your VM.   Because the VM   Public   IP   Address   can   change, you   may   need toredownload the   RDP file after   restarting your VM each time.
For Mac devices: you will also   need to   download and   run   Microsoft   Remote   Desktop from:
https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12Once   it   is installed, you can   run the   RDP file   as   normal.   
Figure   5:   RDP   downloadOnce downloaded,   running the file will   require confirmation.   For Windows, this   confirmation   will   look   like figure 6. The   reason for this   is that   RDP connections   can   be   used   maliciously to   control   someone's   computer.   In this case, since we are just connecting   to   our   Azure   VM, you   should   click   connect.
Figure 6:   Run and   confirm   RDP   connection
Once you’ve confirmed that you want to connect, you   will   have   to   login   (Figure   7)   using   the   password   listed   in the VM description,   in this case   it   is:   info386@wgtn , check   with   your   tutor   to   confirm.   Once submitted,   it’ll ask again   if you want to connect   as the   connection   does   not   have   a   dedicated trusted certificate   (Figure 8). Click yes.   Now you should connect to   your   Virtual   machine.
Figure 7:   Login to your   VM   
Figure 8: Trusted connection
Congratulations! You’ve   logged on to your Virtual   machine and   are controlling   it   via   the   cloud!
Configuring your Virtual   MachineBecause your Virtual   machine   is   running Windows   10 for the first time, you   will   need to   configure   some   basic   privacy details.   None of these settings are   important   for the   workshops,   so   you   can   have   fun   and         choose what you want, you   m代 写INFO386 T1 2022 Workshop 1 Azure - Virtual machineC/C++
代做程序编程语言ay just choose to disable all   of them.   
Figure   9:   Privacy   Settings
Complete any other set-up   requirements for your   new   machine   and   then,   you   should   now   be   on   the Windows   Desktop.   From   here you can treat   it as any other   Windows   10   computer. The   VM-specific controls are at the top of the screen   on   a   blue   bar. These   include   the   controls   to   minimise   and   close   the         RDP connection.   Note, some   keyboard functions you’re   used to,   might   not work the same   way   as   normal   e.g. Alt+Tab will only cycle through applications   in your   VM,   not   between the   VM   and   your   normal   machine. Anytime you want to exit, for example, to   read   the   guide,   use   the   minimise   button   on   the   blue   bar.   
Figure   10: Windows   10    Edge   browser
Operating within your Virtual   machine
Now that you’ve got a fully functioning Windows   10 Virtual   machine,   try   using   it to   browse   the   internet   and set   up your work environment. You can   log onto   Blackboard   or   Facebook.   This   is   your   chance   to play around with afresh Windows   10   computer.
Your   next task   is to   use   Microsoft   Edge, the default   internet   browser that comes   installed with   Windows   10.   Using   Microsoft   Edge,   download your   preferred   browser and   if you’d   like to, a text editor   (Otherwise you’ll   have to   use   notepad).   My   personal   preferences are   Chrome   as the   internet   browser and   Notepad++ as the text editor.   Remember, your VM   is 64   bit   so   download   software   appropriately.
Bonus   Task: See   what the internet looks like,   without a digital   footprint.   Checkout your suggested videos on   YouTube, or search results on generic   terms!
While these are downloading,   look at the   options   on the   blue   bar   at   the   top.   
Figure   11:   Disconnecting from   RDP   connection
The X at the end   is   used to   disconnect   your   machine.
Disconnecting   hasn’t stopped the Virtual   machine. This   is   because disconnecting from the   RDP connection   isn’t   like turning off the computer,   it’s   like turning off the   screen.   However, to   avoid   accidentally   leaving your VM   running, when you disconnect, your virtual   machine will   automatically   stop. As   I   mentioned earlier,a Virtual   machine   left   running without   purpose   is just   using electricity,      depreciating   hardware, and   burning through your time quota,   hence the setting.
This   is your   preferred way of stopping the   machine.   If you wish for the virtual   machine   to   continue   running   in the   background, you will just   need to   minimise the window.
Stopping the Virtual   machine   (Manually)
Once you’ve finished   using your Virtual   machine   (i.e. finished   installing and customising any   software),         close the   RDP connecting and go   back to Azure   Labs.   If you’ve   closed the   web   page   you   may   have to   log   in again. To stop the VM, simply   click the   blue toggle   and   the   status   will   change   from   “Running”   to
“Stopping”   .   It will   not stop   immediately,   but Azure will give a   notification   once the   Virtual   machine   has   successfully stopped.
Stopping the Virtual   machine will   prevent   it from continuing to   use your   quota to   operate,   as   it   is   equivalent to turning off the computer   rather than   merely turning off the   screen.This approach assumes that you   remember to turn   it off everytime   you   stop   using   it.   We   have   setup   an      auto-shutdown of your VM after   15   minutes of   inactivity on   the   machine.   Don’t   worry   if this   catches   you   out, you can always   restart the   machine, as shown   at   the   beginning   of this   guide.
ApacheApache   HTTP Server,   known simply as Apache   is opensource free web   server   software. When   a   visitor      visits the   URL or   URI of your website, Apache will   coordinate the   content   to   present   them   with.   Apache   is still the   most   popular web server.   Based on W3Schools   monthly   web   server   stats,   it   is   used to   run   36.5%   of web servers.   It can   be   used   alongside   PHP to   create   a   dynamic website   and   MySQL to   store   and   manipulate data.
We’re going to get set-up for   next week’s workshop   by   starting to   set-up   Apache.   Make   sure   your   VM   is   running again   if you’ve stopped   it.
Download   C++ and Apache
To operate, Apache   requires C++. As such, the   first   step   is   to   download   both   C++   and   Apache.   Fortunately, we can download them   both from the same   website.
Start   by   visitingwww.apachelounge.com/download/
This   page   includes   both the   download   links for C++   redistributable and Apache   itself   as   shown   in   Fig   12.   
Figure   12:   Download   C++ and   Apache
Once the C++   redistributable   is downloaded   (It should   be   named VC_redist.x64.exe),   double   click   on   it to run.   It will then ask for   permission to   install as   shown   in   Fig   13. Then   download Apache   2.4.53,   remembering we   have an x64   machine.   
Figure   13:   C++   Install
When   installing C++ for the first time,   it will   require the computer   to   restart   the   computer   to   finish the   install.   Make sure that the Apache zip download   is finished when   you   do   this.   When   restarting   the computer, you will   be   disconnected from   RDP. Simply wait and   reconnect.   Once this   is   done, we   can   start setting   up Apache.
This   is something we will   leave for   next week, as   Apache   doesn’t   have   a   set-up wizard   of   its   own,   so   we   will   be   manually doing this!
Completion
This   marks the completion of the guide content.   However,   if you   have   extra time   or   want   an   extra   challenge, try the following challenges.
Challenges
●             Finish setting   up your work-environment within your VM   (File architecture,   Internet   Browser,    Text   Editor).
●          Create   a   basic website   using   HTML    CSS   within your   files.   Don’t   save   to   the   temporary   drive   as   any   files   in   that   drive   will   bede-allocated.







         
加QQ：99515681  WX：codinghelp
