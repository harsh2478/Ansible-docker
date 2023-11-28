# Ansible-docker-container
Explaination :

 Pull Image Task:

 - Name: "Pull image from Docker Hub"

 - Ansible Docker Module Used: docker_image

 - Action: Pulls the Docker image named "vimal13/apache-webserver-php" from Docker Hub.

 - Options:

     1) source: pull: Specifies to pull the image.

     2) state: present: Ensures that the image is present on the host.

     3) timeout: 120: Sets a timeout of 120 seconds for pulling the image.

 Launch Container Task:

 - Name: "Launching container"

 - Ansible Docker Module Used: docker_container

 - Action: Launches a Docker container named "my-apache-container" using the pulled image.

 - Options:

     1) image: "vimal13/apache-webserver-php": Specifies the image to use.

     2) state: present: Ensures that the container is present.

     3) labels: Adds a label "Environment: testing" to the container.

     4) restart_policy: always: Configures the container to restart always if it exits.

     5) volumes: ["/data"]: Mounts the host's "/data" directory into the container.

     6) Registers the output of this task for debugging purposes.

 Debug Task:

 - Name: "Debug information about the Docker container"

 - Ansible Debug Module Used: debug

 - Action: Prints the registered output, which contains information about the launched container.
