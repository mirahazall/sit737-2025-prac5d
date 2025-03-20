- To build the docker image use: "docker build -t calculator-microservice ."

- Before publishing the docker image we need to do a test run on our development computer to make sure everything is in working order. 
- Once we’ve packaged our microservice as a Docker image, we can use the docker run command below to instantiate it as a container. 
- docker run -d -p 3000:3000 -e PORT=3000 calculator-microservice 
- This creates a local instance of our microservice that we can then test using a web browser.

- Use "docker-compose up -d" command to create the container with the image we created and start it.
- This command will read the docker-compose.yml file, pull the necessary images if they're not already available locally, create the containers, and start them.

- To push a Docker image to Google Cloud Platform Container Registry: 
  1. Download Google Cloud CLI to your computer through the link on the GCP website.
  2. After installation completes, run the installation script using the command: "./google-cloud-sdk/install.sh"
  3. Initialize the gcloud CLI by running the command: "./google-cloud-sdk/bin/gcloud init". This command will prompt you to choose the cloud project to use as well as the Compute Region and Zone.
  5. Enter the following command to authenticate with Google Cloud: "gcloud auth login". This command will open an external web window to enable login to your GCP account.
  6. Configure Docker for GCP using the command: "gcloud auth configure-docker"
  7. Tag the docker image using the command: "docker tag calculator-microservice australia-southeast1-docker.pkg.dev/sit737-25t1-yildiz-0226add/hazals-repo/calculator-microservice:latest" (replace the image name, repo name and project name with yours)
  8. Push the docker image to your container registry using the command: "docker push australia-southeast1-docker.pkg.dev/sit737-25t1-yildiz-0226add/hazals-repo/calculator-microservice:latest" (replace the image name, repo name and project name with yours)
  9. To check if the microservice can boot properly from the Docker image you pushed to Google Container Registry, use the docker run command below to start the container and test the microservice:
"docker run -d -p 8080:3000 australia-southeast1-docker.pkg.dev/hazals-repo/sit737-25t1-yildiz-0226add/calculator-microservice:latest" (replace the image name, repo name and project name with yours)






  
