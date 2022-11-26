# Machine Learning on BigData -- is based (a fork) on BigData Solution written in Python based on Hadoop and Spark.

It is a layer on top of Martin Karlsons framework that adds machine learning, data mining, AI and mathematical staticstic capabilites to it, an instance of the framework which runs with upgraded versions 3.2.2 of Spark, 3.5.0 of Jyputerlab and 3.8.4 of Python. 
#### Malin Yamato 大和まりん
Email : yamto@malin.jp 

## objective 
To provide next genration of intensive care methods applying machine learning and artificial intelligece to swiftly provide optinal tratment for intensive care possibvle care for those suffering from multi desise conditions.

### Something like this

![overview][intensive]

### Currenty

![overview][ml2]

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
[intensive] : intensivecare.png
