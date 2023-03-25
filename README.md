# Spring Log Monitoring
This project is a Docker-compose file that starts Elasticsearch, Kibana, and Logstash. It is designed for use with Spring Boot applications that require a logging and search solution.

![520cf765-e177-4e3d-866b-c9c37e993dbf](https://user-images.githubusercontent.com/47903345/227745589-9ea8e0e2-223b-4cb8-ac7f-8f85bffa8b8a.jpeg)

# Prerequisites
Before running this project, make sure you have the following installed:

Docker
Docker-compose
JDK 11 or higher
Maven

# Docker Compose
The services section defines the different containers that make up the application. In this case, there are three services: elasticsearch, kibana, and logstash. Each service has a number of attributes defined, such as the image to use, the container name, environment variables, ports to expose, volumes to mount, and networks to join.

* The elasticsearch service uses the official ElasticSearch Docker image version 8.3.3, sets some environment variables such as bootstrap.memory_lock, and exposes port 9200 to the host. It also mounts the elasticsearch_data volume to store the Elasticsearch data.

* The kibana service uses the official Kibana Docker image version 8.3.3, exposes port 5601 to the host, and sets environment variables to configure Kibana to connect to the Elasticsearch instance.

* The logstash service uses the official Logstash Docker image version 8.3.3, mounts the Logstash configuration files and pipelines from the local file system, exposes several ports, and sets some environment variables to configure Logstash.

* The networks section defines a Docker network called "elastic" which all the containers will join.

* Finally, the volumes section defines the elasticsearch_data volume which will be created by Docker to store the Elasticsearch data.

# Getting Started
1. Clone the repository.
2. Navigate to the root directory in your terminal.
3. docker-compose up
4. The Spring Boot application should now be accessible at http://localhost:8080. Elasticsearch will be available at http://localhost:9200 and Kibana at http://localhost:5601.

# Configuration
The Docker-compose file contains environment variables that configure the services. If you need to change any settings, you can do so by modifying the docker-compose.yml file.

# Acknowledgments
This project was inspired by the official Elasticsearch Docker image and the following blog post: https://www.elastic.co/blog/a-practical-introduction-to-elasticsearch-with-logs.

<!-- CONTACT -->
# Contact
Eray Araz - [@erayaraz](https://www.linkedin.com/in/erayaraz/) - erayaraz10@gmail.com

# License
This project is licensed under the MIT License - see the LICENSE.md file for details.
