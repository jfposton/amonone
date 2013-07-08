Amon Lite has 2 main parts:

* **amond** - A collector daemon 
* **amon** - Web application, that displays the information and captures log and exception information sent from the clients

Amon Lite stores everything in a Mongo database, you can check if that's working by typing <code>mongo</code> in
the terminal. If mongo is working properly, the message that you will see after typing the command
should say <code>Connected to test</code>


 
## Controlling the collector daemon

The collector daemon is started automatically when you boot your operation system. It's located in <code>
/etc/init.d/amond</code> and you can control it with the following commands:

* **status** - returns the current status of the daemon. If Amon Lite is running properly this command should return 
<code> Amon Lite is running as PID ... </code>


* **restart** - restarts the daemon, you should always do that, after altering the configuration file

* **stop**- stops the daemon

* **start** - starts the daemon and displays <code>Amon Lite started as PID ... </code> if successfull

Depending on your operating system, you probably should run these commands as root 
<code>sudo /etc/init.d/amond start|stop|restart</code>

If the daemon doesn't start or is not working properly, you can check */usr/local/amonlite/amond.log* for detailed
information about the problem.

## Controlling the web interface

To save resources, the web interface is not started with your operating system, so you have to start it manually. 
It's located in <code>/etc/init.d/amonlite</code> and you can control it with the following commands:


* **status** - returns the current status of the web app. This command should return 
<code> Amon Lite .. version .. is running as PID. The Amon Lite web interface is running on http://127.0.0.1:2464</code>


* **restart** - restarts the web application

* **stop** - stops the web application

* **start** - starts the web application and displays <code>The Amon Lite web interface is running on http://127.0.0.1:2464 </code>

You can control both the port and the host from the configuration file. The Web interface is *mandatory* if you want to collect log information and exception data.

If the web app doesn't start, you can check */usr/local/amonlite/amon.log* for detailed
information about the problem.


## Modes

You can run Amon Lite in 2 modes:

* **Read-only mode** - this is the default setting.

* **Protected mode** - you can enable it by changing *acl* in /etc/amonlite.conf to "True". In this mode the Amon Lite web app is password protected.

