### how to install tomcat in ubuntu

Step 1: Install Java

# sudo apt-get update

Step 2: Install Tomcat

# sudo apt-get install tomcat7

step 3 : find and replace JAVA_OPTS

# sudo nano /etc/default/tomcat7

JAVA_OPTS="-Djava.security.egd=file:/dev/./urandom -Djava.awt.headless=true -Xmx512m -XX:MaxPermSize=256m -XX:+UseConcMarkSweepGC"

# sudo service tomcat7 restart

# sudo nano /etc/tomcat7/tomcat-users.xml

<tomcat-users>
    <user username="admin" password="password" roles="manager-gui,admin-gui"/>
</tomcat-users>

# sudo service tomcat7 restart


Open in web browser:
http://server_IP_address:8080

___copy__ module you can pass static values to a configuration file but for dynamic values
for that ansible have ___template__ module called jinja template, you can use ___lineinfile__ module if you the regular expression 


