**Jenkins Overview**

**What is Jenkins?**
Jenkins is an open-source automation server widely used to automate parts of software development, including building, testing, and deploying applications. It is written in Java and supports Continuous Integration (CI) and Continuous Delivery (CD), helping development teams deliver software faster and with fewer errors.

---

### 🔧 **Key Features of Jenkins**

* **Open Source** and community-supported.
* **Extensible** with over 1,800 plugins for building, deploying, and automating any project.
* **Cross-platform**: Runs on Windows, macOS, and Linux.
* **Distributed Builds**: Supports master-agent architecture to run builds on multiple machines.
* **Easy Integration** with tools like Git, Docker, Maven, Gradle, Ansible, Kubernetes, etc.

---

### 🚀 **How Jenkins Works**

1. **Developer Pushes Code** to a version control system (e.g., GitHub).
2. **Jenkins Job is Triggered** either manually, by a schedule, or automatically after a code push.
3. **Build is Performed** using specified tools like Maven or Gradle.
4. **Tests are Run** (unit, integration, etc.).
5. **Results are Reported** and optionally, the application is deployed to staging or production.

---

### 📦 **Common Use Cases**

* Automated testing during development.
* Continuous integration for DevOps pipelines.
* Scheduled jobs (e.g., backups, reports).
* Building and deploying Docker containers.
* Deployment to cloud platforms (AWS, Azure, GCP).

---

### 🧱 **Jenkins Architecture**

* **Controller (Master)**: Manages jobs, scheduling, and user interface.
* **Agent (Slave)**: Executes tasks assigned by the controller.
* Jobs can be executed on the controller or on agents distributed across servers.

---

### ✅ **Advantages**

* Saves time by automating repetitive tasks.
* Improves code quality via consistent testing.
* Easy integration with many tools.
* Large community and plugin ecosystem.

---

### ❗ **Challenges**

* Plugin management can become complex.
* Performance issues with too many concurrent jobs.
* Requires maintenance and regular updates for security.

---

### 💡 Example Pipeline (Declarative Jenkinsfile)

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh './build.sh'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './test.sh'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to production...'
                sh './deploy.sh'
            }
        }
    }
}
```

Here is a simple **Jenkins CI/CD pipeline architecture diagram**:

```
                        +------------------+
                        |  Developer Push  |
                        |     (GitHub)     |
                        +--------+---------+
                                 |
                                 v
                        +--------+---------+
                        |     Jenkins      |
                        |   (Controller)   |
                        +--------+---------+
                                 |
                 +---------------+---------------+
                 |               |               |
                 v               v               v
         +-------+-----+ +-------+-----+ +-------+-----+
         |   Build     | |   Test      | |   Deploy    |
         |  Stage      | |  Stage      | |  Stage      |
         +-------------+ +-------------+ +-------------+
                 \               |               /
                  \              |              /
                   \             v             /
                    +-------------------------+
                    |     Notification /      |
                    |     Report Generation   |
                    +-------------------------+
```

### 📌 Description of Flow:

* **Developer Pushes Code** to GitHub or another SCM.
* **Jenkins** detects the change and triggers a pipeline.
* The pipeline runs **Build**, **Test**, and **Deploy** stages.
* Optionally, Jenkins can notify teams (via email, Slack, etc.) and generate reports.


## Project on Jekins
1. start by updating, this checks for the latest versions of packages, so the system knows what updates are available.
```
sudo apt update
```
![caption](/img/1.update.jpg)

2. we will Installs the Java Development Kit (JDK)
```
sudo apt install default-jdk-headless

```
The command:

```bash
sudo apt install default-jdk-headless
```

**does the following:**

---

### 🧱 **Installs the Java Development Kit (JDK) without a GUI**

#### 🔍 Breakdown:

* **`sudo`** – Run the command with administrator privileges.
* **`apt install`** – Tells the system to install the specified package(s).
* **`default-jdk-headless`** – A variant of the default Java Development Kit **without GUI (graphical) components**.


![caption](/img/2.install-jdk.jpg)

3. Then we can now install jekins using the command below
```
    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
    sudo apt update
    sudo apt-get install jenkins

```
![caption](/img/3.install-jekins.jpg)

4. To check if jekins is install and confirm the status of jenkins
```
sudo systemctl status jenkins

```
the image below show jekins is running by showing active
![caption](/img/4.jekins-running.jpg)

5. then we can go to the browser to access jekins Gui by using the command below
```
http://localhost:8080
```
we are able to see a log in page asking for password
![caption](/img/5.localhost-jekins.jpg)

6. To get the password we go to terminal and read the file 
```
cat /var/lib/jekins/secrets/initialAdminPassword
```
then input it into the Unlock jekins web page and submit
![caption](/img/6.jekins-password.jpg)

7. then click install suggested plugins which will start the installation
![caption](/img/7.install-jekins-on-ubuntu.jpg)

8. next is to create admin user and submit
![caption](/img/8.fill-details.jpg)

9. it will display jekins ready
![caption](/img/9.start-using-jekins.jpg)

10. the jekins page
![caption](/img/10.jekins-page.jpg)

We have successfully install Jekins on our ubuntu os. 