<!--
SPDX-FileCopyrightText: Contributors to the Documentation project

SPDX-License-Identifier: Apache-2.0
-->

# FAQ

* **How to start everything up?** Make sure that PostgreSQL is running. Make sure that Apache HTTPD web server and Apache ActiveMQ are running. Then start Apache Tomcat application server as described in the [installation manual](installationguide/setuposgp.md).
* **Where are the log files?** The Apache Tomcat application server logs can be found in `/var/log/tomcat`. The Apache HTTPD web server logs can be found in /var/log/httpd. The PostgreSQL log files can be found in `/var/lib/pgsql/9.3/data/pg_log`. The platform log files can be found in `/var/log/osp/logs/`.
* **Help: SELinux is preventing &lt; something &gt;?** Make sure to set SELinux to 'permissive' mode. Then try again and it should work as SELinux will no longer enforce the current policy. Later, one can use the SELinux tools to create a proper policy that allows everything that was prevented before.
* **How to add or update a component?** Make sure to place the properties file\(s\) for the component in `/etc/osp`. Add the locations of the properties file\(s\) to Apache Tomcat context.xml file. Add the war file to `/usr/share/tomcat/webapps`. Restart Apache Tomcat.
* **How to configure a component?** Most \(if not all\) components of the open smart grid platform are de-coupled using queues. Configure the broker URL in the properties file and take notice of the queues that a component uses/needs. Make sure to double check the connectionstring for PostgreSQL.
* **How to configure URL's for a component?** In this case the Apache HTTPD vhost needs to be updated. The vhost config file can be found in /etc/httpd/conf.d. We use redirects from HTTP to HTTPS and AJP proxy to send the requests to Apache Tomcat.
* **How to check up on Apache ActiveMQ?** Apache ActiveMQ offers a web interface \(the default port is 8161, default credentials: admin/admin\). Using the web interface one can check the queues and especially the dead letter queue \(DLQ\).
* **How do I obtain a public key for a device?** Public Keys are usually manufacterer supplied for Smart Metering. For the Open Source part you can use the OSLP device simulator. In `Sources/OSGP/Config/certificates/oslp/` you can find instructions for generating a OSLP device public key, and a folder with 5 pre-generated keys for test devices.
* **My code gives a lot of errors in Eclipse after importing** Try the following things: run `mvn clean install` in the open-smart-grid-platform directory. Right-click on a project in Eclipse and select 'Maven -&gt; Update project..', select all projects and update.
* **The Vagrant script fails** If you are receiving errors while downloading the ubuntu iso, sources, etc. or if the puppet script does not start; try running the Vagrant script again by typing `vagrant destroy && vagrant up` in the directory with the vagrant file.
* **I want to update my code from Github** If you want to update your code, just run `git pull` in the repository you want to update. You can also create a fresh Virtual Machine using the vagrant installation, this procedure makes sure you have the most recent code.
* **Is a user required to consume platform services?** No, an organization is required.

\_If your question is not in this list, please create an \[issue on Github in the documentation repository \][documentation repository](https://github.com/OSGP/documentation/issues/new?title=Question%20:My%20Title&body=**Question:**%0A%0A**background:**%0A%0A**)

