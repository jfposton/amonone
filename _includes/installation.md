
1. Download the latest stable Amon Lite version from [https://github.com/martinrusev/amonlite/downloads](https://github.com/martinrusev/amonlite/downloads), untar
and install the package with <code>sudo python setup.py install</code>
2. Install the prequisite packages - <code>gcc, sysstat, python-dev</code>, on RPM based 
distributions, the package is called <code>python-devel</code>
4. Copy the configuration file from 
<code><a href='https://raw.github.com/martinrusev/amonlite/master/config/amonlite.conf'>https://raw.github.com/martinrusev/amonlite/master/config/amonlite.conf</a></code>
to <code>/etc/amonlite.conf</code>
3. Copy the system info collect daemon from <code><a href='https://raw.github.com/martinrusev/amonlite/master/contrib/amond'>https://raw.github.com/martinrusev/amonlite/master/contrib/amond</a></code>
to <code>/etc/init.d/amond</code> 
4. Copy the web application daemon from <code><a href='https://raw.github.com/martinrusev/amonlite/master/contrib/amonlite'>https://raw.github.com/martinrusev/amonlite/master/contrib/amonlite</a></code>
to <code>/etc/init.d/amon</code> 
6. Make the daemons executable with <code>sudo chmod +x /etc/init.d/amond /etc/init.d/amon </code>
7. Create a directory for Amon Lite specific log files <code>sudo mkdir /usr/local/amonlite</code>
8. AmonOne stores all the information in a Mongo database. If you already have MongoDB installed, skip this step.
You can install Mongo, following this guide: <a href='http://docs.mongodb.org/manual/installation/'>http://docs.mongodb.org/manual/installation</a>
9. Finally start the Amon Lite collector daemon with <code>sudo /etc/init.d/amond start</code>
10. Add *amond* to the list of processes that boot with the operating system:

 {% highlight bash %}
# For Debian based distributions	
sudo update-rc.d amond defaults

# For RPM based distributions
sudo chkconfig --add amond
{% endhighlight %}
