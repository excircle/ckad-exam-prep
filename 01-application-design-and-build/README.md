# Application Design and Build (20%)

The **Application Design and Build** section of the CKAD exam focuses on the foundational skills needed to design, build, and manage containerized applications within Kubernetes. To excel in this section, candidates must demonstrate proficiency in creating and managing container images, selecting the appropriate Kubernetes workload resources (e.g., Deployments, DaemonSets, CronJobs) for various application use cases, and understanding multi-container Pod design patterns such as sidecars and init containers. Mastery of both ephemeral and persistent storage volumes is essential for ensuring data persistence and proper inter-container communication. This domain emphasizes practical knowledge of building efficient, modular, and scalable applications that align with Kubernetes best practices.

# Challenges

### **1. Define, Build, and Modify Container Images**
- **Exercise: [Build a custom container image](https://github.com/excircle/ckad-exam-prep/blob/main/01-application-design-and-build/challenges/define-build-and-modify-container-images/writeup.md)**
  - Create a `Dockerfile` to:
    - Start with a base image (e.g., `alpine` or `python`).
    - Add application files (e.g., a simple Python or Node.js script).
    - Install necessary dependencies.
    - Define an entry point for the application.
  - Build the image using `docker build`.
  - Push the image to a container registry (e.g., Docker Hub or a private registry).
  - Test the image locally.

- **Exercise: Modify an existing container image**
  - Pull a base image (e.g., `nginx`).
  - Add a custom `index.html` file to the default NGINX directory using a `Dockerfile`.
  - Build and test the modified image.

---

### **2. Choose and Use the Right Workload Resource**
- **Exercise: Create and deploy different Kubernetes workload resources**
  - Create a `Deployment` with 3 replicas for a web application.
  - Create a `DaemonSet` to run a logging agent on all nodes.
  - Schedule a `CronJob` to run a script every minute that writes to a log file.
  - Compare and understand the use cases for each workload resource.

- **Exercise: Modify an existing Deployment**
  - Scale the Deployment from 3 replicas to 5.
  - Update the Deployment image to a newer version using `kubectl set image`.

---

### **3. Understand Multi-Container Pod Design Patterns**
- **Exercise: Create a Pod with sidecar containers**
  - Create a Pod YAML manifest with:
    - A main container running a web application (e.g., `nginx`).
    - A sidecar container that logs HTTP requests to a file.
  - Verify communication between containers using a shared volume.

- **Exercise: Create a Pod with an init container**
  - Create a Pod YAML manifest with:
    - An init container that performs an initialization task (e.g., writing configuration files).
    - A main container that uses the files created by the init container.

---

### **4. Utilize Persistent and Ephemeral Volumes**
- **Exercise: Use an ephemeral volume**
  - Create a Pod that uses an `emptyDir` volume to share data between containers.
  - Write data from one container and read it from another within the same Pod.

- **Exercise: Use a persistent volume**
  - Create a `PersistentVolume` and `PersistentVolumeClaim`.
  - Attach the volume to a Pod.
  - Verify data persistence by deleting and recreating the Pod.

---

### **Challenge Exercise: Comprehensive Scenario**
1. Build a custom image for a Node.js app and push it to a container registry.
2. Create a Deployment that runs the app with 3 replicas.
3. Add a sidecar container for logging.
4. Use a persistent volume to store logs and ensure data is retained across Pod restarts.
5. Scale the Deployment to handle increased traffic.

---

These exercises will prepare you for real-world scenarios and strengthen your ability to perform tasks tested in the CKAD exam. Let me know if you'd like detailed YAML templates or guidance on any of these exercises!