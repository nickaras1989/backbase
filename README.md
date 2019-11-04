For re usability, I have written separate roles for each tasks
Activemq.yml   jdk.yml   nginx.yml  tomcat.yml

1. For nginx deployment with hello world page
   ansible-playbook playbooks/nginx.yml -i inventory/dev.ini

hello world index file has been kept in the templates and default.conf to read the DocumentRoot folder.

Bring down the httpd and nginx service since the use the port 8080

2. For apache tomcat deployment
   ansible-playbook playbooks/tomcat.yml -i inventory/dev.ini

A sample.war file is kept in the files folder, in real case deployment we could bring the sample.war from the artifactory to the tomcat server.
A tomcat.service file is created and stored in the templates for running tomcat as service.

3. cd opt]$   ansible-playbook playbooks/Activemq.yml -i inventory/dev.ini
An activemq.service file is stored in the templates to start ActiveMQ as a service


4. cd opt]$   ansible-playbook playbooks/jdk.yml -i inventory/dev.ini
to install oracle JDK8 and set JAVA_HOME for all users
