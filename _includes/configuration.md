Amon Lite has only one configuration file and you can find it at <code>/etc/amonlite.conf</code>.
The configuration file is in JSON, so after editing it, please check if the syntax is valid at: 
<a href='http://jsonlint.com/'>http://jsonlint.com/</a>

You can find an example configuration file with all the parameters at
<a href='https://raw.github.com/martinrusev/amonlite/master/config/amonlite.conf'>https://raw.github.com/martinrusev/amonlite/master/config/amonlite.conf</a> 


The configuration file has the following parameters:

*  **mongo**  - Configuration options for the mongo backend.
		
	* **port** - The port used to connect to mongo.Default: 27017 

	* **host** - The host where mongo is installed. Default: "127.0.0.1"

* **web_app** - Configuration options for the web interface

	* **host** - The host where the web application is running. Default: "127.0.0.1"

	* **port** - The port where the web application is running. Default: 2464

* **system_check_period** - How often does the daemon collect information, in seconds. Default: 60


* **secret_key** - Random string, generated everytime you install or update Amon Lite. Used for cookies and sessions, when
the authenicaion module is on.

* **timezone** - Amon Lite saves and displays everything in UTC. With this option you can display the data in your local timezone. 
To do that, find your desired timezone at <a href='http://en.wikipedia.org/wiki/List_of_tz_database_time_zones'>
http://en.wikipedia.org/wiki/List_of_tz_database_time_zones</a> and paste the value from the *TZ* row in amonlite.conf


* **proxy** - Controls the base url value ( used in forms and urls through the web app ). 
	
	* Default: "False" - Amon Lite will generate a base_url using the values from web_app:host and web_app:port
	* "True" - base_url is an empty string. Set this value to "True" if you want to run Amon Lite behind a traditional web server like
	nginx or apache