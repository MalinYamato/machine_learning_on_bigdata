# Machine Learning on BigData -- distributed ML related computation bassed on real-time micro-batch streams as well as big-data.  

It is a layer on top of Martin Karlsons framework that adds machine learning, data mining, AI and mathematical staticstic capabilites to it, an instance which runs with upgraded versions 3.3.1 of Spark and PySpark and 3.10.6 of Python. The instance runs on Ubuntu 22.04 insteead of Alpine, which consumes some more resources, but makes the life of intergrating new s/w a great deal less painfu. It is currently capalbe of running most machine learning python packages inculding the model calibration utiility GridSearchCV with the the help of joblibspark, which enablies sckit-learn classes such as GridSearchCV to run on executors on Sparc worker nodes. 

#### Malin Yamato 大和まりん
Email : yamto@malin.jp \
post-graduate student, Artifical Intelligence Applied to Medicine AIM \
Department of Physiology and Pharmaocolgy FYFA, Karolinska Institutet and 
Deparment of Computer and Systems Sciences, Stockholm University

## Objective of this project
To provide next generation of intensive care methods, methods in anasthetics applying machine learning and artificial intelligece to swiftly provide relief and optinal tratment to intensive care possibly care for those suffering from multi desise conditions. sepsis, multplie organ failures.



## Currenty what we have here

![overview][ml2]

## Comming up version 2
###Purpose
To emulate a cluster with haivng services run in docker on a virtual machine each VM with its own ip address. This will make it easeir to add datanode and worker nodes locally or on physical machine by cloing a virtual machine node and deployu it there. 

![overview][v2]

## Vision or Something like this

![overview1][iva]

### Scale your data management by distributing workload and storage on Hadoop and Spark Clusters, explore and transform your data in Jupyter Notebook.

<!--
*** Written by Martin Karlsson
*** www.martinkarlsson.io
-->

[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- ABOUT THE PROJECT -->
## About The Project

Purpose for this tutorial is to show how to get started with Hadoop, Spark and Jupyter for your BigData solution, deploy as Docker Containers.

![Architecture overview][arch]

## Pre-requisite
- Only confirmed working on Linux/Windows (Apple Silicon might have issues).
- Ensure Docker is installed.

## Start

Execute `bash master-build.sh` to start the the build and start the containers.

### Hadoop
Access Hadoop UI on ' http://localhost:9870 '

### Spark
Access Spark Master UI on ' http://localhost:8080 '

### Jupyter
Access Jupyter UI on ' http://localhost:8888 '

<!-- CONTRIBUTING -->
## Contributing

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/featureName`)
3. Commit your Changes (`git commit -m 'Add some featureName'`)
4. Push to the Branch (`git push origin feature/featureName`)
5. Open a Pull Request


<!-- CONTACT -->
## Contact

### Martin Karlsson

LinkedIn : [martin-karlsson][linkedin-url] \
Twitter : [@HelloKarlsson](https://twitter.com/HelloKarlsson) \
Email : hello@martinkarlsson.io \
Webpage : [www.martinkarlsson.io](https://www.martinkarlsson.io)


Project Link: [github.com/martinkarlssonio/big-data-solution](https://github.com/martinkarlssonio/big-data-solution)


<!-- MARKDOWN LINKS & IMAGES -->
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-malin]: ttps://www.linkedin.com/in/malin-yamato-l%C3%A4%C3%A4kk%C3%B6-randstr%C3%B6m-5032041a3/
[linkedin-url]: https://linkedin.com/in/martin-karlsson
[arch]: arch.png
[ml2]: ml2.png
[iva]: iva3.png
[v2]: MLDB.png


