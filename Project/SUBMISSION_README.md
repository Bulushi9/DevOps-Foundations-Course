## Multi-Container Docker Application with CI/CD: Calculator App Project

#### Complete Project Instructions: [DevOps Foundations Course/Project](https://github.com/shiftkey-labs/DevOps-Foundations-Course/tree/master/Project)

#### Submission by - **<BASIM> <ALBULUSHI>**

### Project Overview

- **Brief project description:** What is the purpose of your application?

Simple calculator with React frontend and Pyhton Flask backend. The application does basic arithmatic operations.


- **Which files are you implmenting? and why?:**

- backend > Dockerfile, the backend of the application and it has the deployment environment
- backend > requirements.txt, list of the dependencies which are needed to run the application

- frontend > Dockerfile, to add the frontend deployment for the application

- docker-compose.yml, connects the front and backend of the application

- _**Any other explanations for personal note taking.**_

N/A


### Docker Implementation

**Explain your Dockerfiles:**

- **Backend Dockerfile** (Python API):

    - backend > Dockerfile, sets up the Python environment for the Flask API backend, installs dependencies, and exposes port 5000.

- **Frontend Dockerfile** (React App):
    - frontend > Dockerfile, sets up the Node.js environment for the React frontend, installs dependencies, and exposes port 3000. 

**Use this section to document your choices and steps for building the Docker images.**


### Docker Compose YAML Configuration

**Break down your `docker-compose.yml` file:**

- **Services:** List the services defined. What do they represent?
- **Networking:** How do the services communicate with each other?
- **Volumes:** Did you use any volume mounts for persistent data?
- **Environment Variables:** Did you define any environment variables for configuration? 

**Use this section to explain how your services interact and are configured within `docker-compose.yml`.**

- **Services:** 
    - backend: Represents the Flask API backend service running on port 5000.
    - frontend: Represents the React frontend service running on port 3000

- **Networking:** 
    - Both services are connected through a default Docker network which enables communication between the frontend and backend.
- **Volumes:** 
    - N/A
- **Environment Variables:** it used flask_env and flask_app


### CI/CD Pipeline (YAML Configuration)

**Explain your CI/CD pipeline:**

- What triggers the pipeline (e.g., push to main branch)?
- What are the different stages (build, test, deploy)?
- How are Docker images built and pushed to a registry (if applicable)?

**Use this section to document your automated build and deployment process.**

- What triggers the pipeline (e.g., push to main branch)?
    - They are triggered by pull or push requests
- What are the different stages (build, test, deploy)?
    - Build: Builds Docker images for both the frontend and backend services.
    - Test: Runs unit tests to verify the correctness of the application.
    - Deploy: Deploys the application by spinning up containers using Docker Compose.
- How are Docker images built and pushed to a registry (if applicable)?
    - During the build stage, the pipeline pulls base images, installs dependencies, and builds images for both services. The images can optionally be pushed to a Docker registry for deployment in a production environment.

### Assumptions

- List any assumptions you made while creating the Dockerfiles, `docker-compose.yml`, or CI/CD pipeline. 

- The application does not require a database.
- Default network configuration provided by Docker Compose is enough for service communication.
- The pipeline does not include additional testing frameworks or static analysis tools due to the simplicity of the application.


### Lessons Learned

- What challenges did you encounter while working with Docker and CI/CD?
- What did you learn about containerization and automation?

**Use this section to reflect on your experience and learnings when implementing this project.**

- What challenges did you encounter while working with Docker and CI/CD?
    - Managing multiple services with Docker Compose was initially tricky but improved with practice.
    - Debugging issues related to npm dependencies in the frontend Dockerfile took some time.

- What did you learn about containerization and automation?
    - Containerization simplifies deployment and ensures consistent environments across different machines.
    - CI/CD pipelines enhance productivity by automating repetitive tasks like building and testing the application

### Future Improvements

- How could you improve your Dockerfiles, `docker-compose.yml`, or CI/CD pipeline? 
- (Optional-Just for personal reflection) Are there any additional functionalities you would like to consider for the calculator application to crate more stages in the CI/CD pipeline or add additional configuration in the Dockerfiles?

**Use this section to brainstorm ways to enhance your project.**

Nothing so far.

<!-- BEST OF LUCK! -->
