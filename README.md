Project description
---------------------------------

The aim of this work is to develop a complete system of collection, management and
analysis of crowdsourced information concerning HTTP traffic data.

Internet traffic via HTTP can be recorded by any client, so that the data can be used later to analyze the behavior of a site. For this purpose, the HAR (HTTP ARchive) template has been created, which defines a specific structure (schema) JSON to store this data.

Although analyzing the data of a computer is not so interesting, the analysis of HAR files from many computers, involving many websites and different access times, has the potential to reveal very interesting aspects of the World Wide Web infrastructure.
Thus, the purpose of this work is to build a population-based HAR data collection system in order to provide some basic analyzes for each user individually, but also more general analyzes concerning the internet infrastructure in an area (eg Athens). In the system
There are two types of users: Administrator and User.

USER
----
1) Registration in the system. The user registers and accesses the system by choosing a username & password of his choice, and providing his email. The password is required
be at least 8 characters long and contain at least one capital letter, a number and a symbol (eg # $ * & @).

2) Upload data. The user selects a HAR file from his computer. The file will be edited locally to delete sensitive data and then the user has two options: a) Upload it to the system or b) Save the edited file locally. If the file is uploaded to the system, the uploaded data must be further processed (on the server) in order to save the desired data in the appropriate format. Also, the IP of the user uploading the file should be "analyzed" so that the user's connectivity provider is automatically discovered and this information is stored in the database along with the registrations.

3) Profile management. The user can change the username / password and see basic statistics for the data he has uploaded (date of last upload, number of registrations)

4) Data visualization. The user can see on a map the locations of the IPs to which he has sent HTTP requests. Specifically, a heatmap is displayed on the map that shows
the distribution of the number of records related to HTML, PHP, ASP, JSP web objects (or pure domains, without path).

ADMINISTRATOR
----
1) Display of Basic Information. The administrator sees relevant information on one page,
in tables and / or graphs depicting:
  a. The number of registered users
  b. The number of entries in the database by type (method) of application
  c. The number of entries in the database by response code (status)
  d. The number of unique domains that exist in the database
  e. The number of unique connectivity providers in the database
  f. The average age of the web objects at the time they were retrieved, per CONTENT-TYPE

2) Data visualization (object entries). The administrator can see on a map the locations of the IPs to which he has sent HTTP requests. Specifically, one appears
marker per IP, with lines connecting each user's source city with each icon. The thickness of the lines is adjusted according to the number of requests made to the specific IP, normalized to the maximum number made to the most popular IP.


In the present project, the protection of sensitive data has been taken into account, so that only the information needed from the har files is stored in the database, ip - api and ipstack have been used to retrieve the ip, while for the display of the information on maps it has use the plugin leafletjs

