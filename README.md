# Deploy-Java-Application-on-Tomcat-Server

## Create a Virtual Machine on AWS

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/b36a94f6-4b09-4d5c-b2d2-e9c683fcafb2)

## Connect this machine to the server using Mobaxterm and install tomcat in the /opt

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/24c6c29f-de58-46cd-bcf1-a2b34be626f1)

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/c90eec59-cfc3-4758-b9d1-20c4e18f63a2)

## Extract the tar file so that the file can be executable. 

Use the command tar xvzf filename

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/9a758893-aa21-43ff-bdf0-a7f9bf2eae66)

## Make some modifications on the configuration directory of the extracted file

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/de01a83e-c932-46e3-b9ca-36bf9e7cb99b)

These modifications are related to the username and password and need to be done on the tomcat-users.xml inside the cd /opt/apache-tomcat-9.0.76/conf/

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/c8328fe5-cdf0-4196-b822-6e0376d6bbf2)

## Create alias 

sudo ln -s /opt/apache-tomcat-9.0.76/bin/startup.sh /usr/bin/startTomcat
sudo ln -s /opt/apache-tomcat-9.0.76/bin/shutdown.sh /usr/bin/stopTomcat

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/617cf79c-84f4-4795-a481-2a747e874740)


## Open the context.xml file and comment

Inside the webapps directory, we have 2 files that need to be modified: manager and host-manager 
sudo vi /opt/apache-tomcat-9.0.76/webapps/manager/META-INF/context.xml

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/ce1ca08e-f590-4fed-aa7d-4bf6b2cd413f)

sudo vi /opt/apache-tomcat-9.0.76/webapps/host-manager/META-INF/context.xml


## Stop the tomcat and start it again

- install Java and maven first so that we can define the variable otherwise we will received an error message when we will try

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/2782f061-6bca-4c24-b7ea-79034d7fe38f)

For start and stop Tomcat, use sudo stopTomcat and sudo startTomcat

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/869c72c2-17d3-4c0d-aa03-01e945748bfe)

## Access the tomcat application from the browser

By default Tomcat runs on 8080

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/e03fbb68-1d76-4e5b-a6e7-eb7fa2f7a654)

Tomcat is running

## Build our application

Clone the repository https://github.com/jaiswaladi246/Petclinic.git

-Go to cd Petclinic

![1](https://github.com/adrydry/Deploy-Java-Application-on-Tomcat-Server/assets/102819001/5066c943-7dd5-43cf-b679-ff1c88a78ec2)

- apply the command mvn clean package

## Troubleshooting
- We install Tomcat without installing java. we noticed an error message related to the path of Java. 
- when trying accessing Tomcat from the server, we received an error message. We discovered that the port 8080 wasn't open in the security group. We correct it





