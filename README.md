# Ansible-docker-container
Explaination :

- Pull Image Task:

 - Name: "Pull image from Docker Hub"

 - Ansible Docker Module Used: docker_image

 - Action: Pulls the Docker image named "vimal13/apache-webserver-php" from Docker Hub.

 - Options:

  - source: pull: Specifies to pull the image.

  - state: present: Ensures that the image is present on the host.

  - timeout: 120: Sets a timeout of 120 seconds for pulling the image.

- Launch Container Task:

 - Name: "Launching container"

 - Ansible Docker Module Used: docker_container

 - Action: Launches a Docker container named "my-apache-container" using the pulled image.

 - Options:

  - image: "vimal13/apache-webserver-php": Specifies the image to use.

  - state: present: Ensures that the container is present.

  - labels: Adds a label "Environment: testing" to the container.

  - restart_policy: always: Configures the container to restart always if it exits.

  - volumes: ["/data"]: Mounts the host's "/data" directory into the container.

  - Registers the output of this task for debugging purposes.

- Debug Task:

 - Name: "Debug information about the Docker container"

 - Ansible Debug Module Used: debug

 - Action: Prints the registered output, which contains information about the launched container.
