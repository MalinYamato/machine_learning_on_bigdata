# Machine Learning on BigData -- distributed ML related computation bassed on real-time micro-batch streams as well as big-data.  

It is a layer on top of Martin Karlsons framework that adds machine learning, data mining, AI and mathematical staticstic capabilites to it, an instance which runs with upgraded versions 3.3.1 of Spark and PySpark and 3.10.6 of Python. The instance runs on Ubuntu 22.04 insteead of Alpine, which consumes some more resources, but makes the life of intergrating new s/w a great deal less painfu. It is currently capalbe of running most machine learning python packages inculding the model calibration utiility GridSearchCV with the the help of joblibspark, which enablies sckit-learn classes such as GridSearchCV to run on executors on Sparc worker nodes. 

#### Malin Yamato 大和まりん
Email : yamto@malin.jp \
post-graduate student, Artifical Intelligence Applied to Medicine AIM \
Department of Physiology and Pharmaocolgy FYFA, Karolinska Institutet and 
Deparment of Computer and Systems Sciences, Stockholm University

## Objective of this project
To provide next generation of intensive care methods, methods in anasthetics applying machine learning and artificial intelligece to swiftly provide relief and optinal tratment to intensive care possibly care for those suffering from multi desise conditions. sepsis, multplie organ failures.

## Currenty what we have here and the vision, the goal

![overview][ml2]![overview1][iva]

## Comming up version 2
### Purpose
To emulate a cluster with haivng services run in docker on a virtual machine each VM with its own ip address. This will make it easeir to add datanode and worker nodes locally or on physical machine by cloing a virtual machine node and deployu it there. 

![overview3][v2]

## Pre-requisite
- this is ony tested on debian based Linux distributions, It should work on all Linuxes and I see no reson for it not to work on Windows.
- latest Docker and VirtualBox

## Recommended harware requirements
- 32 GB RAM 
- 8 core CPU

## Start

Execute `bash master-build.sh` to start the the build and start the containers.

### Hadoop
Access Hadoop UI on ' http://localhost:9870 '

### Spark
Access Spark Master UI on ' http://localhost:8080 '

### Jupyter
Access Jupyter UI on ' http://localhost:8888 '

[linkedin-malin]: ttps://www.linkedin.com/in/malin-yamato-l%C3%A4%C3%A4kk%C3%B6-randstr%C3%B6m-5032041a3/
[ml2]: ml2.png
[iva]: iva3.png
[v2]: MLBD.png


