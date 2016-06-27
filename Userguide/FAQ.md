##2.5 FAQ

- **How to start everything up?** Make sure that PostgreSQL is running. Make sure that Apache HTTPD web server and Apache ActiveMQ are running. Then start Apache Tomcat application server.
- **Where are the log files?** The Apache Tomcat application server logs can be found in /var/log/tomcat7. The Apache HTTPD web server logs can be found in /var/log/httpd. The PostgreSQL log files can be found in /var/lib/pgsql/9.3/data/pg_log.
- **Help: SELinux is preventing < something >?** Make sure to set SELinux to 'permissive' mode. Then try again and it should work as SELinux will no longer enforce the current policy. Later, one can use the SELinux tools to create a proper policy that allows everything that was prevented before.
- **How to add or update a component?** Make sure to place the properties file(s) for the component in /etc/osp. Add the locations of the properties file(s) to Apache Tomcat context.xml file. Add the war file to /usr/share/tomcat7/webapps. Restart Apache Tomcat.
- **How to configure a component?** Most (if not all) components of OSGP are de-coupled using queues. Configure the broker URL in the properties file and take notice of the queues that a component uses/needs. Make sure to double check the connectionstring for PostgreSQL.
- **How to configure URL's for a component?** In this case the Apache HTTPD vhost needs to be updated. The vhost config file can be found in /etc/httpd/conf.d. We use redirects from HTTP to HTTPS and AJP proxy to send the requests to Apache Tomcat.
- **How to check up on Apache ActiveMQ?** Apache ActiveMQ offers a web interface (the default port is 8161). Using the web interface one can check the queues and especially the dead letter queue (DLQ).
- _If your question is not in this list, please fire an [issue on github ](https://github.com/OSGP/Config/issues/new?title=Question:My%20Title&)_
