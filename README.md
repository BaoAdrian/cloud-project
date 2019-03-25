# Cloud-Based IoT Web API
Cloud-serviced web application aimed to manage and utilize Internet-of-Things devices using Python, Amazon AWS, and a MySQL Database.

Specifications: https://lecturer-russ.appspot.com/classes/cs346/spring19/projects/proj02.pdf

# Project Description
There are three main parts for this application. 
<ol>
  <li> MySQL Database </li>
  <li> Amazon EC2 Instances Running Apache Webserver </li>
  <li> Python/HTML Web Application </li>
</ol>

Amazon AWS is used to manage the MySQL Database instance using their RDS Service as well as the EC2 Instances that will be configured and loaded with our Web application and all required dependencies to perform SQL queries through interactions with the Web application. The web application is developed using python and makes heavy usage of the CGI framework to generate dynamically generate HTML based on the shared state of the instances.



# Helpful Links
This link contains an API that we might be able to use to control the state of the lightbulb:
https://iot.mozilla.org/things/

This link shows Amazons IoT Management platform that we could possibly use to manage the devices using AWS.
https://aws.amazon.com/iot-device-management/

Maybe we can integrate one of these buttons once we get it working. Could do some cool stuff with it. https://aws.amazon.com/iotbutton/ 



# Video Examples
Here is a tutorial on connecting an IoT device and managing it using their dashboard. Not quite related to what we are trying to do since he is using JavaScript and some Edison device/ Robot Sphere but interesting to see how to interact with the console to 'develop' and 'test' the implementation.
https://www.youtube.com/watch?v=_0us6NzlaoQ



# Brainstorm
<h2> Servers </h2>
https://aws.amazon.com/ec2/

- 2 EC2 Instance that will have the python/html code installed with all dependencies on them and will point to the RDS DB Instance when connecting to MySQL Database.


<h2> Web application </h2> 
- HTML generated through python scripts. 
- Idea: Break the development into stages...  
  <ol>
  <li>Simple button that controls on/off power for the bulb (amazon 'thing')  </li>
  <li>Querying the database for pre-set RBG values (maybe some rgb sliders) </li>
  <li>If possible, configure Amazon Alexa to have programmed commands for colors configs </li>
  </ol>
  
  
<h2> Amazon MySQL DB </h2> 
  https://aws.amazon.com/getting-started/tutorials/create-mysql-db/
- MySQL for database, connected via Amazon RDS to our instances (WIP).
- Database will be its own instance.

<ul>  
  <li>Endpoint: project2-iot-lightbulb.ccdjm6mfovyw.us-west-1.rds.amazonaws.com</li>
  <li>username: Admin </li>
  <li>password: project2password</li>
  <li>DBName: project2-iot-lightbulb</li>
</ul>

# Development - Milestones
Database:
- [x] Create MySQL DB Instance 
- [x] Link DB Instance to MySQL Workbench
- [x] Save important params for access into the python web application


Server:
- [x] Successfully launch Amazon EC2 
- [ ] Install python application on EC2 instances
  - [ ] Connect DB instance to EC2 instances   


Web Application:
- [ ] HTML Mockup
- [ ] CGI/Python application that generates HTML
  - [ ] On/Off swith
  - [ ] Table of RGB Configs & RGB Slider & Brightness/Saturation Slider
  - [ ] Possible integration with Amazon Alexa


Miscellaneous:
- [ ] Figure out if Amazon IoT Management API is required to handle communication between device and web application. (I.E. register device as 'thing' in the API and perform calls to database through interface.
